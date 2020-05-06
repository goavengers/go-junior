<div align="center">
  <h1>Go Junior</h1>
  <h5>We will help you, join!</h5>
</div>

### Как установить Go?

1. Скачайте исходники: `wget https://dl.google.com/go/go$VERSION.$OS-$ARCH.tar.gz`
2. Распакуйте: `tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz`
3. Установите переменные окружения.

> Для этого откройте ваш `.profile` файл и добавьте следующие 3 строки в конец файла. Вы можете добавить это в файл `.zshrc` или `.bashrc` в соответствии с вашей конфигурацией оболочки.

```bash
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

4. Выполните, чтобы изменения вступили в силу: `source ~/.profile` или `.bashrc`, `.zshrc` - это позволит использовать команды go без перезапуска сеанса.
