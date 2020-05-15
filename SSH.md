## Работа с ssh-agent

0. В примерах используется редактор `mcedit`, вы можете использовать любой какой пожелаете.
1. Проверяем конфигурацию ssh: `mcedit ~/.ssh/config` и настраиваем конфигурацию следующим образом:
    ```shell script
    Host *
    ForwardAgent Yes
    ```
    * Так же можно настроить глобально (не обязательно):  `mcedit /etc/ssh/ssh_config` - раскомментировать необходимые строки как выше
2. Проверяем наличие ssh keys: `ssh-add -l` & `ssh-add -L`
    * Вы должны узреть нечто следующее:
    ```shell script
    // 1
   2048 SHA256:ZpgJVijAqVzEGX4WrGSfhXlx0iVgWcwYe26lQY12RnY /home/user/.ssh/id_rsa (RSA)
   
    // 2
   ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCz3h/.../dwkRqDhNLtBs7ZJY/SI9i/5hRXF/home/user/.ssh/id_rsa
    ```
    * Если ключей нет генерируем новые:  `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` все пункты по-дефолту
    * Добавляем в настройки github аккаунта сгенерированный публичный ключ из: `~/.ssh/id_rsa.pub` по адресу: `https://github.com/settings/keys`
    * Чтобы посмотреть ключ воспользуйтесь командой: `cat ~/.ssh/id_rsa.pub`
3. Запустите ssh-agent в фоновом режиме: `eval "$(ssh-agent -s)"`
    * Вы увидите примерно следуещее: `> Agent pid 59566`
4. Добавьте свой закрытый ключ SSH в ssh-agent: `ssh-add` можно так же добавлять определенный ключ, например: `ssh-add ~/.ssh/id_rsa`
5. Выполняем второй пункт еще раз.
6. Коннектимся к удаленному серверу и выполняем команды из второго пункта.
7. Если 6 пункт успешен (т.е. результат как на 2 пункте) вы можете провести тестовый git clone проекта.

#### Troubleshooting

Если у вас ничего не работает, могут возникнуть некоторые проблемы с правами, это не так очевидно. Для SSH права доступа к файлу могут быть слишком открыты. Проверьте: `cd ~/.ssh && ls -ls`
```shell script
// как примерно должены выглядеть правильные права, а не 777 : -rwxrwxrwx

4 -rw------- 1 root root  394 мар 23 11:37 authorized_keys
4 -rw------- 1 root root 1679 мая 17  2019 id_rsa
4 -rw-r--r-- 1 root root  394 мая 17  2019 id_rsa.pub
4 -rw-r--r-- 1 root root 3104 мар 23 13:03 known_hosts
```
Закрытый ключ должен иметь права на чтение и запись только для пользователя и другие разрешения для группы и других.

`chmod 600 ~/.ssh/id_rsa`

Аналогично, открытый ключ не должен иметь права на запись и выполнение для группы и других.

`chmod 644 ~/.ssh/id_rsa.pub`

Это исправление должно помочь исправить ошибку: Permission denied (publickey) в ssh.

## Проход на внутренние сервера через SSH (ssh-proxy)

```
k_alekseev@me0w:[~]: cat .ssh/config | tail -n 13
Host ci.iptv2022.com
  ForwardAgent yes
Host ci.iptv2022.com
  HostName ci.iptv2022.com
  User root
Host server_base
  HostName 194.35.48.15
  User root
  ProxyCommand ssh -q root@ci.iptv2022.com nc %h %p
Host 194.35.48.15
  HostName 194.35.48.15
  User root
  ProxyCommand ssh -q root@ci.iptv2022.com nc %h %p
4:46
k_alekseev@me0w:[~]: ssh server_base
root@server_base:~#
```

#### PS

Для переброски по цепочке нужно на каждом узле активировать forwarding.

## Настрйока безпарольного доступа к серверам

Генерируем ключи:

1. `ssh-keygen`
    * После ввода этой команды вы должны увидеть следующий вывод:
    ```shell script
    enerating public/private rsa key pair.
    Enter file in which to save the key (/home/user/.ssh/id_rsa):
    ```
    * Если ранее вы уже генерировали пару SSH ключей, вы можете увидеть следующий вывод:
    ```shell script
    /home/user/.ssh/id_rsa already exists.
    Overwrite (y/n)?
    ```
    * Если вы выберете перезаписать ключи на диск, вы **не сможете** использовать старые ключи для аутентификации. 
2. Копирование публичного ключа на сервер: 
    `cat ~/.ssh/id_rsa.pub | ssh user@host "mkdir -p ~/.ssh && touch ~/.ssh/authorized_keys && chmod -R go= ~/.ssh && cat >> ~/.ssh/authorized_keys"`
    * Здесь создается диреткория `~/.ssh`, если она не существует
    
#### PS
 
Вы можете копировать не только ключи, хранящиеся в id_rsa.pub, но и в других файлах.
Поздравляем у вас настроен вход по ключам SSH, позволяющий заходить на сервер без использования пароля.

## Проверка настройки

Если ваши ключи правильно прописаны на github, то выполнив на локальном компьютере `ssh git@github.com -T`

Вы увидите приветсвие с вашим именем, например:
```
> ssh git@github.com -T
Hi dapi! You've successfully authenticated, but GitHub does not provide shell access.
```

Если у вас правильно настроен `ssh-agent`, то вы увидете такое-же приветсвие если выполните `ssh git@github.com -T` из консоли на сервере на который зашли через `ssh`
