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
# <a name="interpolated-strings"></a><span data-ttu-id="72964-103">Интерполированные строки</span><span class="sxs-lookup"><span data-stu-id="72964-103">Interpolated strings</span></span>

<span data-ttu-id="72964-104">Интерполяция строк — это [строки](strings.md) , которые позволяют внедрять в них выражения F #.</span><span class="sxs-lookup"><span data-stu-id="72964-104">Interpolated strings are [strings](strings.md) that allow you to embed F# expressions into them.</span></span> <span data-ttu-id="72964-105">Они полезны в широком спектре сценариев, где значение строки может изменяться в зависимости от результата значения или выражения.</span><span class="sxs-lookup"><span data-stu-id="72964-105">They are helpful in a wide range of scenarios where the value of a string may change based on the result of a value or expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="72964-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72964-106">Syntax</span></span>

```fsharp
$"string-text {expr}"
$"string-text %format-specifier{expr}"
$"""string-text {"embedded string literal"}"""
```

## <a name="remarks"></a><span data-ttu-id="72964-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="72964-107">Remarks</span></span>

<span data-ttu-id="72964-108">Интерполяция строк позволяет писать код в "отверстиях" внутри строкового литерала.</span><span class="sxs-lookup"><span data-stu-id="72964-108">Interpolated strings let you write code in "holes" inside of a string literal.</span></span> <span data-ttu-id="72964-109">Простой пример:</span><span class="sxs-lookup"><span data-stu-id="72964-109">Here's a basic example:</span></span>

```fsharp
let name = "Phillip"
let age = 30
printfn $"Name: {name}, Age: {age}"

printfn $"I think {3.0 + 0.14} is close to {System.Math.PI}!"
```

<span data-ttu-id="72964-110">Содержимое между каждой `{}` парой фигурных скобок может быть любым выражением F #.</span><span class="sxs-lookup"><span data-stu-id="72964-110">The contents in between each `{}` brace pair can be any F# expression.</span></span>

<span data-ttu-id="72964-111">Для экранирования `{}` пары фигурных скобок запишите два из них следующим образом:</span><span class="sxs-lookup"><span data-stu-id="72964-111">To escape a `{}` brace pair, write two of them like so:</span></span>

```fsharp
let str = $"A pair of braces: {{}}"
// "A pair of braces: {}"
```

## <a name="typed-interpolated-strings"></a><span data-ttu-id="72964-112">Типизированные строки с интерполяцией</span><span class="sxs-lookup"><span data-stu-id="72964-112">Typed interpolated strings</span></span>

<span data-ttu-id="72964-113">У интерполяции строк также могут быть спецификаторы формата F # для обеспечения безопасности типов.</span><span class="sxs-lookup"><span data-stu-id="72964-113">Interpolated strings can also have F# format specifiers to enforce type safety.</span></span>

```fsharp
let name = "Phillip"
let age = 30

printfn $"Name: %s{name}, Age: %d{age}"

// Error: type mismatch
printfn $"Name: %s{age}, Age: %d{name}"
```

<span data-ttu-id="72964-114">В предыдущем примере код ошибочно передает `age` значение `name` , где должно быть, и наоборот.</span><span class="sxs-lookup"><span data-stu-id="72964-114">In the previous example, the code mistakenly passes the `age` value where `name` should be, and vice/versa.</span></span> <span data-ttu-id="72964-115">Так как в интерполяции строк используются описатели формата, это ошибка компиляции вместо незаметной ошибки времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="72964-115">Because the interpolated strings use format specifiers, this is a compile error instead of a subtle runtime bug.</span></span>

<span data-ttu-id="72964-116">Все описатели формата, представленные в формате [обычного текста](plaintext-formatting.md) , допустимы внутри строки с интерполяцией.</span><span class="sxs-lookup"><span data-stu-id="72964-116">All format specifiers covered in [plaintext formatting](plaintext-formatting.md) are valid inside of an interpolated string.</span></span>

## <a name="verbatim-interpolated-strings"></a><span data-ttu-id="72964-117">Буквальные строки с интерполяцией</span><span class="sxs-lookup"><span data-stu-id="72964-117">Verbatim interpolated strings</span></span>

<span data-ttu-id="72964-118">F # поддерживает буквальные интерполяции строк с тройными кавычками, чтобы можно было внедрять строковые литералы.</span><span class="sxs-lookup"><span data-stu-id="72964-118">F# supports verbatim interpolated strings with triple quotes so that you can embed string literals.</span></span>

```fsharp
let age = 30

printfn $"""Name: {"Phillip"}, Age: %d{age}"""
```

## <a name="aligning-expressions-in-interpolated-strings"></a><span data-ttu-id="72964-119">Выровняйте выражения в строках с интерполяцией</span><span class="sxs-lookup"><span data-stu-id="72964-119">Aligning expressions in interpolated strings</span></span>

<span data-ttu-id="72964-120">Можно выровняйте выражения по левому краю или по правому краю в строках с интерполяцией `|` и определить, сколько пробелов.</span><span class="sxs-lookup"><span data-stu-id="72964-120">You can left-align or right-align expressions inside interpolated strings with `|` and a specification of how many spaces.</span></span> <span data-ttu-id="72964-121">Следующая интерполяция строки выровняйте левое и правое выражения влево и вправо соответственно по семи пробелам.</span><span class="sxs-lookup"><span data-stu-id="72964-121">The following interpolated string aligns the left and right expressions to the left and right, respectively, by seven spaces.</span></span>

```fsharp
printfn $"""|{"Left",-7}|{"Right",7}|"""
// |Left   |  Right|
```

## <a name="interpolated-strings-and-formattablestring-formatting"></a><span data-ttu-id="72964-122">Интерполяция строк и `FormattableString` форматирования</span><span class="sxs-lookup"><span data-stu-id="72964-122">Interpolated strings and `FormattableString` formatting</span></span>

<span data-ttu-id="72964-123">Можно также применить форматирование, которое соответствует правилам для <xref:System.FormattableString> :</span><span class="sxs-lookup"><span data-stu-id="72964-123">You can also apply formatting that adheres to the rules for <xref:System.FormattableString>:</span></span>

```fsharp
let speedOfLight = 299792.458
printfn $"The speed of light is {speedOfLight:N3} km/s."
// "The speed of light is 299,792.458 km/s."
```

<span data-ttu-id="72964-124">Кроме того, интерполяция строки также может быть помечена как тип с <xref:System.FormattableString> помощью аннотации типа:</span><span class="sxs-lookup"><span data-stu-id="72964-124">Additionally, an interpolated string can also be type checked as a <xref:System.FormattableString> via a type annotation:</span></span>

```fsharp
let frmtStr = $"The speed of light is {speedOfLight:N3} km/s." : FormattableString
// Type: FormattableString
// The speed of light is 299,792.458 km/s.
```

<span data-ttu-id="72964-125">Обратите внимание, что аннотация типа должна быть в самом строковом выражении.</span><span class="sxs-lookup"><span data-stu-id="72964-125">Note that the type annotation must be on the interpolated string expression itself.</span></span> <span data-ttu-id="72964-126">F # не выполняет неявное преобразование строки с интерполяцией в <xref:System.FormattableString> .</span><span class="sxs-lookup"><span data-stu-id="72964-126">F# does not implicitly convert an interpolated string into a <xref:System.FormattableString>.</span></span>

## <a name="see-also"></a><span data-ttu-id="72964-127">См. также</span><span class="sxs-lookup"><span data-stu-id="72964-127">See also</span></span>

* [<span data-ttu-id="72964-128">Строки</span><span class="sxs-lookup"><span data-stu-id="72964-128">Strings</span></span>](strings.md)
