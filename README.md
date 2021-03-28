<div align="center">
  <h1>Go Junior</h1>
  <h5>Возможно вы заблудились и искали официальную документацию, но поверьте у нас не хуже - тут есть все-что нужно новичкам, плюс вкусняшечки! :sunglasses:</h5>
</div>

### Содержание

- [x] [Основные особенности языка](#features)
- [x] [Как установить Go?](#how_to_install)
- [x] [Управление версиями Go](#version_control)
- [x] [Что дальше?](#what_s_next)
  - [x] [Конкурентность](#what_s_next_concurrency)
  - [x] [gRPC](#what_s_next_grpc)
  - [x] [Полезные ништячки](#what_s_next_useful)
  - [x] [Roadmap golang developer](#what_s_next_roadmap)
- [x] [Подводные камни Go для начинающих](#darker_corners)
  - [x] [Операторы](#darker_corners_operators)
     - [x] [Инкремент и декремент](#darker_corners_operators_1)
     - [x] [Тернарный оператор](#darker_corners_operators_2)
  - [x] [Константы](#darker_corners_constants)
     - [x] [iota](#darker_corners_constants_1)

__Go__ или __GoLang__ — компилируемый многопоточный язык программирования. Язык был разработан Google для решения проблем корпорации, возникающих при разработке программного обеспечения.

<a name="features"></a> **Основные особенности языка:**

- __Ортогональность__ — в языке есть небольшое число средств, не повторяющих функциональность друг друга.
- __Простая грамматика__ — минимум ключевых слов, легко разбираемая структура и читаемый код.
- __Простая работа с типами__ — типизация обеспечивает безопасность, но не превращается в бюрократию.
- Отсутствие неявных преобразований.
- Сборка мусора.
- Встроенные простые и эффективные средства распараллеливания.
- Чёткое разделение интерфейса и реализации.
- Быстрая сборка за счёт эффективной системы пакетов с явным указанием зависимостей.

### <a name="how_to_install"></a>  Как установить Go?

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

### <a name="version_control"></a>  Управление версиями Go

Используйте [goenv](https://github.com/syndbg/goenv), чтобы выбрать версию Go для своего приложения и гарантировать, что ваша среда разработки соответствует производственной.

### <a name="what_s_next"></a>  Что дальше?

- [A Tour of Go](https://tour.golang.org/welcome/1)
- [Golang - изучаем зяык программирования GO](https://golangs.org/)
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

### <a name="what_s_next_concurrency"></a> Конкурентность

- [Concurrency in Go (book)](https://github.com/goavengers/go-junior/raw/master/books/Concurrency%20in%20Go.pdf)
- [Состояние гонки по данным и способы решения](https://www.sohamkamani.com/blog/2018/02/18/golang-data-race-and-how-to-fix-it/)
- [Использование контекстов для того, чтобы избежать утечек горутин](https://rakyll.org/leakingctx/)
- [Паттерны конкурентности в Go: пайплайны и отмены](https://blog.golang.org/pipelines)
- [Туториал: Синхронизация состояния с мьютексами в Go](https://kylewbanks.com/blog/tutorial-synchronizing-state-with-mutexes-golang)
- [Буферизованные каналы в Go: советы и рекомендации](https://www.rapidloop.com/blog/golang-channels-tips-tricks.html)

### <a name="what_s_next_grpc"></a> gRPC

- [Видеоурок о gRPC](https://youtu.be/VtX9w8uKvEk)
- [Токен авторизация в микросервисах Go | Token Based Authentication in Go Microservices](http://learningprogramming.net/golang/microservices/token-based-authentication-in-go-microservices/)
- [Написание и использование interveptors](https://medium.com/@shijuvar/writing-grpc-interceptors-in-go-bf3e7671fe48)

### <a name="what_s_next_useful"></a> Полезные ништячки

- [Modern Make](https://makefile.site/)
- [What is REST](https://restfulapi.net/)
- [Двенадцать факторов](https://12factor.net/ru/)
- [Semantic Versioning](https://semver.org/)
- [Шпаргалка по git-flow](https://danielkummer.github.io/git-flow-cheatsheet/index.ru_RU.html)
- [ведите changelog](https://keepachangelog.com/ru/1.0.0/)
- [Работа с ssh-agent](SSH.md)

### <a name="what_s_next_roadmap"></a> Roadmaps

- [Roadmap to becoming a Go developer](https://github.com/Alikhll/golang-developer-roadmap)

### <a name="darker_corners"></a>  Подвоные камни языка Go для начинающих

#### <a name="darker_corners_operators"></a> Операторы

<a name="darker_corners_operators_1"></a> **1. Инкремент и декремент**

В отличие от многих других языков, таких как, JS, PHP, Java и т.д., Go не имеет префиксных операторов увеличения (инкремент) или уменьшения (декремент):

```go
var i int
++i // syntax error: unexpected ++, expecting }
--i // syntax error: unexpected --, expecting }
```

Хотя в Go и есть постфиксные версии этих операторов, но их нельзя использовать в выражениях:

```go
slice := []int{1,2,3}
i := 1
slice[i++] = 0 // syntax error: unexpected ++, expecting :
```

<a name="darker_corners_operators_2"></a> **2. Тернарный оператор**

Наверное одна из самых частых вещей, которые ищут разработчики перешедшие с других языков - это тернарный оператор. Но тут все просто - его нет. Разработчики языка Go решили, что этот оператор часто приводит к некрасивому коду, и лучше вообще его не использовать.

#### <a name="darker_corners_constants"> Константы

<a name="darker_corners_constants_2">**iota**

- Ключевое слово iota представляет последовательные целочисленные константы 0, 1, 2,…
- Оно обнуляется каждый раз, когда const появляется в исходном коде
- И увеличивается после каждой спецификации const.

```go
const (
    C0 = iota
    C1 = iota
    C2 = iota
)
fmt.Println(C0, C1, C2) // "0 1 2"
```

Можно упростить до:

```go
const (
    C0 = iota
    C1
    C2
)
```

Двойное использование йоты не сбрасывает нумерацию:

```go
const (
    C0 = iota // 0
    C1 // 1
    C2 = iota // 2
)
```

Чтобы начать список констант с 1 вместо 0, можно использовать iota в арифметическом выражении.

```go
const (
    C1 = iota + 1
    C2
    C3
)
fmt.Println(C1, C2, C3) // "1 2 3"
```

Можно использовать пустой идентификатор, чтобы пропустить значение в списке констант.

```go
const (
    C1 = iota + 1
    _
    C3
    C4
)
fmt.Println(C1, C3, C4) // "1 3 4"
```

Полный тип enum со строками [best practice]. Вот идиоматический способ реализации перечисляемого типа:

- создаем новый целочисленный тип,
- перечисляем его значения с использованием iota,
- реализуем для типа функцию String.

```go
type Direction int

const (
    North Direction = iota
    East
    South
    West
)

func (d Direction) String() string {
    return [...]string{"North", "East", "South", "West"}[d]
}
```

```go
// usage

var d Direction = North
fmt.Print(d)
switch d {
case North:
    fmt.Println(" goes up.")
case South:
    fmt.Println(" goes down.")
default:
    fmt.Println(" stays put.")
}
// Output: North goes up.
```

> По стандартному соглашению об именовании, необходимо использовать смешанный caps и для для констант. 
> Например, экспортируемую константу будет правильным назвать NorthWest, а не NORTH_WEST.

Другое распространенное приложение для iota — реализация bitmask. 
Это небольшой набор булевых значений (их часто называют “флагами”), которые представлены битами в одном числе.

Посмотрите [bitmasks](https://yourbasic.org/golang/bitmask-flag-set-clear/) и флаги для полного понимания.
