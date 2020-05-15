<div align="center">
  <h1>Go Junior</h1>
  <h5>Возможно вы заблудились и искали официальную документацию, но поверьте у нас не хуже - тут есть все-что нужно новичкам, плюс вкусняшечки! :sunglasses:</h5>
</div>

### Как установить Go?

1. Скачайте исходники: `wget https://dl.google.com/go/go$VERSION.$OS-$ARCH.tar.gz`

> Чтобы понять для какой архитектуры и какую версию Go скачивать посетите сайт: https://golang.org/dl/

2. Распакуйте: `tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz`
3. Установите переменные окружения.

> Для этого откройте ваш `.profile` файл и добавьте следующие 3 строки в конец файла. Вы можете добавить это в файл `.zshrc` или `.bashrc` в соответствии с вашей конфигурацией оболочки.

```bash
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

4. Выполните, чтобы изменения вступили в силу: `source ~/.profile` или `.bashrc`, `.zshrc` - это позволит использовать команды go без перезапуска сеанса.

### Управление версиями Go

Используйте [goenv](https://github.com/syndbg/goenv), чтобы выбрать версию Go для своего приложения и гарантировать, что ваша среда разработки соответствует производственной.

### Что дальше?

- [A Tour of Go](https://tour.golang.org/welcome/1)
- [How to Write Go Code](https://golang.org/doc/code.html)
- [Effective Go](https://golang.org/doc/effective_go.html) | [Эффективный Go](https://github.com/Konstantin8105/Effective_Go_RU)
- [Маленькая книга о Go – Глава 1: Основы](https://sefus.ru/little-go-book-1/)
- [Awesome Go](https://github.com/avelino/awesome-go)
- [Modern Make](https://makefile.site/)
- [What is REST](https://restfulapi.net/)
- [Двенадцать факторов](https://12factor.net/ru/)
- [Semantic Versioning](https://semver.org/)


