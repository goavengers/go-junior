<div align="center">
  <h1>Go Junior</h1>
  <h5>Возможно вы заблудились и искали официальную документацию, но поверьте у нас не хуже - тут есть все-что нужно новичкам, плюс вкусняшечки! :sunglasses:</h5>
</div>

__Go__ или __GoLang__ — компилируемый многопоточный язык программирования. Язык был разработан Google для решения проблем корпорации, возникающих при разработке программного обеспечения.

**Основные особенности языка:**

- __Ортогональность__ — в языке есть небольшое число средств, не повторяющих функциональность друг друга.
- __Простая грамматика__ — минимум ключевых слов, легко разбираемая структура и читаемый код.
- __Простая работа с типами__ — типизация обеспечивает безопасность, но не превращается в бюрократию.
- Отсутствие неявных преобразований.
- Сборка мусора.
- Встроенные простые и эффективные средства распараллеливания.
- Чёткое разделение интерфейса и реализации.
- Быстрая сборка за счёт эффективной системы пакетов с явным указанием зависимостей.

### Как установить Go?

1. Скачайте исходники: `$ wget https://dl.google.com/go/go$VERSION.$OS-$ARCH.tar.gz`

> Чтобы понять для какой архитектуры и какую версию Go скачивать посетите сайт: https://golang.org/dl/

2. Распакуйте: `$ tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz`
3. Установите переменные окружения.

> Для этого откройте ваш `.profile` файл и добавьте следующие 3 строки в конец файла. Вы можете добавить это в файл `.zshrc` или `.bashrc` в соответствии с вашей конфигурацией оболочки.

```bash
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
```

P.S. `$ echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.profile`

4. Выполните, чтобы изменения вступили в силу: `source ~/.profile` или `.bashrc`, `.zshrc` - это позволит использовать команды go без перезапуска сеанса.

### Управление версиями Go

Используйте [goenv](https://github.com/syndbg/goenv), чтобы выбрать версию Go для своего приложения и гарантировать, что ваша среда разработки соответствует производственной.

### Что дальше?

- [A Tour of Go](https://tour.golang.org/welcome/1)
- [How to Write Go Code](https://golang.org/doc/code.html)
- [Effective Go](https://golang.org/doc/effective_go.html) | [Эффективный Go](https://github.com/Konstantin8105/Effective_Go_RU)
- [Маленькая книга о Go – Глава 1: Основы](https://sefus.ru/little-go-book-1/)
- [Awesome Go](https://github.com/avelino/awesome-go)
- [Идиомы Go | Idiomatic Go](https://dmitri.shuralyov.com/idiomatic-go)
- [Основные комментарии, возникающие при ревью кода | Go Code Review Comments](https://github.com/golang/go/wiki/CodeReviewComments)
- [Организация программного кода | Organizing Go code](https://blog.golang.org/organizing-go-code)
- [Пословицы Go | Go Proverbs](https://go-proverbs.github.io/)
- [Структуризация тестов | Structuring Tests in Go](https://medium.com/@benbjohnson/structuring-tests-in-go-46ddee7a25c)
- [Стандартный шаблон пакета | Standard Package Layout](https://medium.com/@benbjohnson/standard-package-layout-7cdbc8391fc1#.h1wq1b1yt)
- [Анатомия проекта на Go | The anatomy of a Go project](https://darian.af/post/the-anatomy-of-a-golang-project/)
- [Руководства по стилю для пакетов Go | Style guideline for Go packages](https://rakyll.org/style-packages/)
- [Обработка времени в go | time in go](https://bl.ocks.org/joyrexus/a56717634a672dcdfd48)
- [Как использовать интерфейсы в Go | How to use interfaces in Go](https://jordanorelli.com/post/32665860244/how-to-use-interfaces-in-go)
- [Лучшие практики Go, шесть лет в деле](https://habr.com/ru/company/mailru/blog/301036/)
- [Отличительные особенности хорошей библиотеки на языке Go](https://medium.com/@cep21/aspects-of-a-good-go-library-7082beabb403)
- [Код-стайл в Go](https://github.com/golang/go/wiki/CodeReviewComments)
- [Шпаргалка по слайсам | Go Slice Tricks Cheat Sheet](https://ueokande.github.io/go-slice-tricks/)

### Конкурентность

- [Состояние гонки по данным и способы решения](https://www.sohamkamani.com/blog/2018/02/18/golang-data-race-and-how-to-fix-it/)
- [Использование контекстов для того, чтобы избежать утечек горутин](https://rakyll.org/leakingctx/)
- [Паттерны конкурентности в Go: пайплайны и отмены](https://blog.golang.org/pipelines)
- [Туториал: Синхронизация состояния с мьютексами в Go](https://kylewbanks.com/blog/tutorial-synchronizing-state-with-mutexes-golang)
- [Буферизованные каналы в Go: советы и рекомендации](https://www.rapidloop.com/blog/golang-channels-tips-tricks.html)

### gRPC

- [Видеоурок о gRPC](https://youtu.be/VtX9w8uKvEk)
- [Токен авторизация в микросервисах Go | Token Based Authentication in Go Microservices](http://learningprogramming.net/golang/microservices/token-based-authentication-in-go-microservices/)
- [Написание и использование interveptors](https://medium.com/@shijuvar/writing-grpc-interceptors-in-go-bf3e7671fe48)

### Полезные ништячки

- [Modern Make](https://makefile.site/)
- [What is REST](https://restfulapi.net/)
- [Двенадцать факторов](https://12factor.net/ru/)
- [Semantic Versioning](https://semver.org/)
- [Шпаргалка по git-flow](https://danielkummer.github.io/git-flow-cheatsheet/index.ru_RU.html)
- [ведите changelog](https://keepachangelog.com/ru/1.0.0/)
- [Работа с ssh-agent](SSH.md)


