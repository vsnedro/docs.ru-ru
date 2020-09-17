---
title: Асинхронные рабочие потоки
description: 'Узнайте о поддержке в языке программирования F # для асинхронного выполнения вычислений, которые выполняются без блокировки выполнения другой работы.'
ms.date: 08/15/2020
ms.openlocfilehash: 14146cc8a643f31831475075212cc06da5f8d6ff
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720274"
---
# <a name="asynchronous-workflows"></a>Асинхронные рабочие процессы

В этой статье описывается поддержка в F # для выполнения вычислений асинхронно, то есть без блокировки выполнения другой работы. Например, асинхронные вычисления можно использовать для написания приложений, которые имеют пользовательские интерфейсы, которые продолжают реагировать на запросы пользователей, так как приложение выполняет другую работу.

## <a name="syntax"></a>Синтаксис

```fsharp
async { expression }
```

## <a name="remarks"></a>Remarks

В предыдущем синтаксисе вычисление, представленное, настроено `expression` для асинхронного выполнения, то есть без блокировки текущего вычислительного потока при выполнении асинхронных операций сна, ввода-вывода и других асинхронных операций. Асинхронные вычисления часто запускаются в фоновом потоке, а выполнение продолжаются в текущем потоке. Выражение имеет тип `Async<'T>` , где `'T` — тип, возвращаемый выражением при `return` использовании ключевого слова. Код в таком выражении называется *асинхронным блоком*или *асинхронным*блоком.

Существует множество способов программирования в асинхронном режиме, а [`Async`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html) класс предоставляет методы, поддерживающие несколько сценариев. Общий подход заключается в создании `Async` объектов, представляющих вычисления или вычисления, которые необходимо выполнять асинхронно, а затем запускайте эти вычисления с помощью одной из функций запуска. Различные функции, запускаемые триггерами, предоставляют различные способы выполнения асинхронных вычислений, и какое из них зависит от того, хотите ли вы использовать текущий поток, фоновый поток или объект задачи .NET Framework, а также наличие функций продолжения, которые должны выполняться после завершения вычисления. Например, чтобы запустить асинхронное вычисление в текущем потоке, можно использовать [`Async.StartImmediate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#StartImmediate) . Когда вы запускаете асинхронное вычисление из потока пользовательского интерфейса, вы не блокируете главный цикл событий, который обрабатывает действия пользователя, такие как нажатия клавиш и действия мыши, чтобы приложение оставалось реагировать на запросы.

## <a name="asynchronous-binding-by-using-let"></a>Асинхронная привязка с помощью let!

В асинхронном рабочем процессе некоторые выражения и операции являются синхронными, а некоторые — более длинными вычислениями, которые предназначены для асинхронного возврата результатов. При асинхронном вызове метода вместо обычной `let` привязки используется `let!` . Результат `let!` заключается в том, чтобы обеспечить продолжение выполнения в других вычислениях или потоках при выполнении вычислений. После того как правая часть `let!` привязки возвращаются, остальная часть асинхронного рабочего процесса возобновляет выполнение.

В следующем коде показано различие между `let` и `let!` . Строка кода, в которой используется, `let` просто создает асинхронное вычисление как объект, который можно запустить позднее с помощью, например `Async.StartImmediate` или [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) . Строка кода, в которой используется, `let!` начинает вычисление, а затем поток приостанавливается до тех пор, пока результат не станет доступным, после чего выполнение продолжится.

```fsharp
// let just stores the result as an asynchronous operation.
let (result1 : Async<byte[]>) = stream.AsyncRead(bufferSize)
// let! completes the asynchronous operation and returns the data.
let! (result2 : byte[])  = stream.AsyncRead(bufferSize)
```

Кроме `let!` того, можно использовать `use!` для выполнения асинхронных привязок. Разница между и совпадает с `let!` `use!` разностью между `let` и `use` . Для `use!` объект удаляется при закрытии текущей области. Обратите внимание, что в текущем выпуске языка F # не `use!` позволяет инициализировать значение null, хотя это и `use` делает.

## <a name="asynchronous-primitives"></a>Асинхронные примитивы

Метод, выполняющий одну асинхронную задачу и возвращающий результат, называется *асинхронным примитивом*, и они предназначены специально для использования с `let!` . В основной библиотеке F # определены несколько асинхронных примитивов. Два таких метода для веб-приложений определяются в модуле [`FSharp.Control.WebExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html) : [`WebRequest.AsyncGetResponse`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncGetResponse) и [`WebClient.AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) . Оба примитива загружают данные с веб-страницы по указанному URL-адресу. `AsyncGetResponse` создает `System.Net.WebResponse` объект и `AsyncDownloadString` создает строку, ПРЕДСТАВЛЯЮЩУЮ код HTML для веб-страницы.

В модуль включаются несколько примитивов для асинхронных операций ввода-вывода [`FSharp.Control.CommonExtensions`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html) . Эти методы расширения `System.IO.Stream` класса являются [`Stream.AsyncRead`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncRead) и [`Stream.AsyncWrite`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-commonextensions.html#AsyncWrite) .

Можно также написать собственные асинхронные примитивы, определив функцию, полный текст которой заключен в блок async.

Для использования асинхронных методов в .NET Framework, предназначенных для других асинхронных моделей с асинхронной моделью программирования F #, создается функция, возвращающая объект F # `Async` . Библиотека F # содержит функции, упрощающие это.

Сюда входит один пример использования асинхронных рабочих процессов; в документации есть множество других методов [класса Async](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html).

В этом примере показано, как использовать асинхронные рабочие процессы для параллельного выполнения вычислений.

В следующем примере кода функция `fetchAsync` получает текст HTML, возвращаемый веб-запросом. `fetchAsync`Функция содержит асинхронный блок кода. Если привязка выполняется к результату асинхронного примитива, в данном случае [`AsyncDownloadString`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-webextensions.html#AsyncDownloadString) `let!` используется вместо `let` .

Функция используется [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) для выполнения асинхронной операции и ожидания ее результата. Например, можно выполнить несколько асинхронных операций параллельно, используя [`Async.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#Parallel) функцию вместе с `Async.RunSynchronously` функцией. `Async.Parallel`Функция принимает список `Async` объектов, настраивает код для каждого `Async` объекта задачи для параллельного выполнения и возвращает `Async` объект, представляющий параллельное вычисление. Точно так же, как и для одной операции, вы вызываете, `Async.RunSynchronously` чтобы начать выполнение.

`runAll`Функция запускает три асинхронных рабочих процесса в параллельном режиме и ожидает до завершения всех.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet8003.fs)]

## <a name="see-also"></a>См. также

- [Справочник по языку F#](index.md)
- [Выражения вычисления](computation-expressions.md)
- [Класс Control. Async](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html)
