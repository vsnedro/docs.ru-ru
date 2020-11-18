---
title: Интерполированные строки
description: 'Сведения о интерполяции строк, специальную форму строки, которая позволяет внедрять выражения F # непосредственно внутри них.'
ms.date: 11/12/2020
ms.openlocfilehash: 8c552b44cea7d6c51ec333b6bdd4d407c6f10da7
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829691"
---
# <a name="interpolated-strings"></a>Интерполированные строки

Интерполяция строк — это [строки](strings.md) , которые позволяют внедрять в них выражения F #. Они полезны в широком спектре сценариев, где значение строки может изменяться в зависимости от результата значения или выражения.

## <a name="syntax"></a>Синтаксис

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a>Remarks

Интерполяция строк позволяет писать код в "отверстиях" внутри строкового литерала. Простой пример:

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

Содержимое между каждой `{}` парой фигурных скобок может быть любым выражением F #.

Для экранирования `{}` пары фигурных скобок запишите два из них следующим образом:

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a>Типизированные строки с интерполяцией

У интерполяции строк также могут быть спецификаторы формата F # для обеспечения безопасности типов.

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

В предыдущем примере код ошибочно передает `age` значение `name` , где должно быть, и наоборот. Так как в интерполяции строк используются описатели формата, это ошибка компиляции вместо незаметной ошибки времени выполнения.

Все описатели формата, представленные в формате [обычного текста](plaintext-formatting.md) , допустимы внутри строки с интерполяцией.

## <a name="verbatim-interpolated-strings"></a>Буквальные строки с интерполяцией

F # поддерживает буквальные интерполяции строк с тройными кавычками, чтобы можно было внедрять строковые литералы.

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a>Выровняйте выражения в строках с интерполяцией

Можно выровняйте выражения по левому краю или по правому краю в строках с интерполяцией `|` и определить, сколько пробелов. Следующая интерполяция строки выровняйте левое и правое выражения влево и вправо соответственно по семи пробелам.

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a>Интерполяция строк и `FormattableString` форматирования

Можно также применить форматирование, которое соответствует правилам для <xref:System.FormattableString> :

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

Кроме того, интерполяция строки также может быть помечена как тип с <xref:System.FormattableString> помощью аннотации типа:

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

Обратите внимание, что аннотация типа должна быть в самом строковом выражении. F # не выполняет неявное преобразование строки с интерполяцией в <xref:System.FormattableString> .

## <a name="see-also"></a>См. также

* [Строки](strings.md)
