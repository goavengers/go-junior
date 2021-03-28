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
  - [x] [Срезы и массивы](#darker_corners_array_slice)
     - [x] [Массивы (slice)](#darker_corners_array_slice_1)
     - [x] [Срезы (array)](#darker_corners_array_slice_2)
  - [ ] Карты
     - [ ] Порядок итерации карты случайный (на самом деле нет)
     - [ ] Проверка наличия ключа карты
     - [ ] Карта - это указатель
     - [ ] Зачем используют значение пустой стурктуры вместо булева
     - [ ] Емкость карты
     - [ ] Значения карты не адресуются
     - [ ] Гонки данных
     - [ ] sync.Map
  - [ ] Строки и байтовые массивы
     - [ ] Основы строк в Go
     - [ ] Строки не могут быть нулевыми (nil)
     - [ ] Строки неизменяемы (вроде)
     - [ ] Строки против среза []byte
     - [ ] UTF-8 и фсе такое
     - [ ] Кодировка строк в Go
     - [ ] Руны, что это
     - [ ] Оператор строкового индекса или оператор for ... range
  - [ ] Циклы песни льда и пламени (нет)
     - [ ] Итератор диапазона (range) возвращает два значения
     - [ ] Переменные итератора цикла используются повторно
     - [ ] Именованные break и continue
  - [ ] Погружение в switch и select
     - [ ] Операторы case по умолчанию прерываются
     - [ ] Именованные break
  - [ ] Функции
     - [ ] Отложенные (defer)
     - [ ] Горутины (goroutines), что это такое **
     	- [ ] Программа не ждет запущенных горутин
     	- [ ] Паникующая горутина приведет к сбою всего приложения, вот ***
  - [ ] Интерфейсы
  - [ ] Наследование (почти ООП. кек)
  - [ ] Операторы равенства, проверка на равенство, равенство во всем мире, мы топим за ра.., стоп не туда
  - [ ] Менеджмент памяти
  - [ ] Логирование
  - [ ] Дата и время

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

<a name="darker_corners_constants_1">**iota**

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

#### <a name="darker_corners_array_slice"> Срезы и массивы

В Go срезы и массивы служат аналогичной цели. Они декларируются примерно так же одинаково:

```go
slice := []int{1, 2, 3}
array := [3]int{1, 2, 3}
// let the compiler work out array length
// this will be an equivalent of [3]int
array2 := [...]int{1, 2, 3} 
fmt.Println(slice, array, array2)
```

Срезы являются более "продвинутыми" и удобными (по факту срез содержит указатель на массив, об этом чуть ниже), по этой причине массивы используют реже и в каких-то специфических случаях. В самых обычных случаях вы также будете использовать срезы.

<a name="darker_corners_array_slice_1"> **Массивы**

Массив - это типизированный набор памяти фиксированного размера. 
Массивы разной длины считаются разными несовместимыми типами.
- В отличие от C, элементы массива инициализируются нулевыми значениями при создании массива, поэтому нет необходимости делать это явно. 
- Также, в отличие от C в Go, массив - это тип значения. Это не указатель на первый элемент блока памяти. Если вы передадите массив в функцию, будет скопирован весь массив. Вы все равно можете передать указатель на массив, чтобы он не копировался.

<a name="darker_corners_array_slice_2"> **Срезы**

Это очень полезная структура данных, но, возможно, немного необычная. Есть несколько способов выстрелить им себе в ногу, всех которых можно избежать, если вы знаете, как срез работает изнутри. 

Вот так выглядит срез исходном коде Go:

```go
type slice struct {
    array unsafe.Pointer
    len   int
    cap   int
}
```

Сам срез является типом значения, но он ссылается на массив, который он использует, с помощью указателя. В отличие от массива, если вы передадите срез в функцию, вы получите копию указателя массива, свойств `len` и `cap` но данные самого массива не будут скопированы и обе копии (оригинал и в функции) среза будут указывать на один и тот же массив. 

То же самое происходит, когда вы "разрезаете" срез. Нарезка создает новый срез, который по-прежнему указывает на тот же массив:

```go
func f1(s []int) {
    // slicing the slice creates a new slice
    // but does not copy the array data
    s = s[2:4] 
    // modifying the sub-slice
    // changes the array of slice in main function as well
    for i := range s {
        s[i] += 10
    }
    fmt.Println("f1", s, len(s), cap(s))
}

func main() {
    s := []int{1, 2, 3, 4, 5}
    // passing a slice as an argument
    // makes a copy of the slice properties (pointer, len and cap)
    // but the copy shares the same array
    f1(s)
    fmt.Println("main", s, len(s), cap(s))
}

Output:

in function f1 [13 14] 2 3
in function main [1 2 13 14 5] 5 5
```

Мы передали срез в фнкцию, "разрезали" (под-срез) его и изменили значения последнего и, как видно, мы изменили оригинальный срез, который находится на самом верхнем уровне в `main`.

Чтобы получить копию среза с данными, вам нужно немного поработать. Вы можете вручную скопировать элементы в новый фрагмент или использовать `copy` или `append`:

```go
func f1(s []int) {
    s = s[2:4]
    s2 := make([]int, len(s))
    copy(s2, s)

    // or if you prefer less efficient, but more concise version:
    // s2 := append([]int{}, s[2:4]...)

    for i := range s2 {
        s2[i] += 10
    }

    fmt.Println("f1", s2, len(s2), cap(s2))
}

func main() {
    s := []int{1, 2, 3, 4, 5}
    f1(s)
    fmt.Println("main", s, len(s), cap(s))
}

Output:

in function f1 [13 14] 2 3
in function main [1 2 3 4 5] 5 5
```

Как видим, оригинальный срзе не изменился, т.к. мы скопировали и он больше не указывает на массив первого среза.

Самым полезным свойством среза является то, что он управляет ростом массива за вас. 
Когда срезу необходимо превысить емкость существующего массива, Go выделит совершенно новый массив с дополнительной емкостью и переместит данные в него (точнее это сделает функция append). 
Но это является еще одной ловушкой, например, если вы ожидаете что два среза будут указывать на один и тот же массив.

```go
func main() {
    // make a slice with length 3 and capacity 4
    s := make([]int, 3, 4)

    // initialize to 1,2,3
    s[0] = 1
    s[1] = 2
    s[2] = 3

    // capacity of the array is 4
    // adding one more number fits in the initial array
    s2 := append(s, 4)

    // modify the elements of the array
    // s and s2 still share the same array
    for i := range s2 {
        s2[i] += 10
    }

    fmt.Println(s, len(s), cap(s))    // [11 12 13] 3 4
    fmt.Println(s2, len(s2), cap(s2)) // [11 12 13 14] 4 4

    // this append grows the array past its capacity
    // new array must be allocated for s3
    s3 := append(s2, 5)

    // modify the elements of the array to see the result
    for i := range s3 {
        s3[i] += 10
    }

    fmt.Println(s, len(s), cap(s)) // still the old array [11 12 13] 3 4
    fmt.Println(s2, len(s2), cap(s2)) // the old array [11 12 13 14] 4 4

    // array was copied on last append [21 22 23 24 15] 5 8
    fmt.Println(s3, len(s3), cap(s3)) 
}
```

Еще одной приятной особенностью является то, что срезы не нужно проверять на нулевое значение и не всегда нужно инициализировать. Такие функции, как `len`, `cap` и `append`, отлично работают с нулевым срезом:

```go
func main() {
    var s []int // nil slice
    fmt.Println(s, len(s), cap(s)) // [] 0 0
    s = append(s, 1)
    fmt.Println(s, len(s), cap(s)) // [1] 1 1
}
```

Но, надо помнить, что пустой срез - это не то же самое, что нулевой срез:

```go
func main() {
    var s []int // this is a nil slice
    s2 := []int{} // this is an empty slice

    // looks like the same thing here:
    fmt.Println(s, len(s), cap(s)) // [] 0 0
    fmt.Println(s2, len(s2), cap(s2)) // [] 0 0

    // but s2 is actually allocated somewhere
    fmt.Printf("%p %p", s, s2) // 0x0 0x65ca90
}
```

Еще одна ловушка, когда вы инициализируете срез через `make`:

```go
s := make([]int, 3)
s = append(s, 1)
s = append(s, 2)
s = append(s, 3)
```

Как вы думаете, что будет? Вот так выглядит сигнатура `make` для срезов:

```go
func make([]T, len, cap) []T
```

Конечно, он инициализирует срез с длиной 3 и емкостью! Т.е. по факту мы сделали следующее: 

```go
s := make([]int, 3, 3)
...
```

И вывод кода выше будет следующим:

```go
[0 0 0 1 2 3]
```

Это может привести к неожиданным ошибка, если не понимать работу срезов. Чтобы код выше вывел ожидаемые 1,2,3, нам необходимо изменить инициализацию через `make` след. образомм:

```go
s := make([]int, 0, 3)
...

// [1 2 3]
```

Иногда встречаются варианты с индексированным доступом, что тоже в принципе верно и вполне рабочее:

```go
s := make([]int, 3, 3)
    	
for i, v := range []int{1, 2, 3} {
	s[i] = v
}
	
fmt.Println(s)
```

Ну и напоследок покажу многомерные срезы, собственно это же можно проделать и с массивами:

```go
x := 2
y := 3
s := make([][]int, y)

for i := range s {
    s[i] = make([]int, x)
}

fmt.Println(s) // [[0 0] [0 0] [0 0]]
```
