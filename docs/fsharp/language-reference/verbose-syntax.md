---
title: Подробный синтаксис
description: Изучите разницу между многословным и легким синтаксисом на языке программирования F.
ms.date: 05/16/2016
ms.openlocfilehash: 722807695c56beb0d681b95a78ed8cb8c1df3ddf
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463906"
---
# <a name="verbose-syntax"></a><span data-ttu-id="bc1cd-103">Подробный синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc1cd-103">Verbose Syntax</span></span>

<span data-ttu-id="bc1cd-104">Для многих конструкций на языке F-образного языка доступны две формы синтаксиса: *многословный синтаксис* и *легкий синтаксис.*</span><span class="sxs-lookup"><span data-stu-id="bc1cd-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="bc1cd-105">Многословный синтаксис не так часто используется, но имеет то преимущество, что менее чувствителен к отступам.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="bc1cd-106">Легкий синтаксис короче и использует отступы для сигнала начала и конца `begin`конструкций, а не дополнительные ключевые слова, как , `end`, `in`и так далее.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="bc1cd-107">Синтаксис по умолчанию — это легкий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="bc1cd-108">В этой теме описывается синтаксис для конструкций F-из, когда легкий синтаксис не включен.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="bc1cd-109">Синтеза Verbose всегда включен, так что даже если вы включите легкий синтаксис, вы все равно можете использовать многословный синтаксис для некоторых конструкций.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="bc1cd-110">Можно отключить легкий синтаксис `#light "off"` с помощью директивы.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="bc1cd-111">Таблица конструкций</span><span class="sxs-lookup"><span data-stu-id="bc1cd-111">Table of Constructs</span></span>

<span data-ttu-id="bc1cd-112">В следующей таблице показан легкий и многословный синтаксис для языковых конструкций f в контекстах, где есть разница между этими двумя формами.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="bc1cd-113">В этой таблице угловые скобки ()&lt;&gt;прилагают элементы синтаксиса, поставляемого пользователем.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="bc1cd-114">Для получения более подробной информации о синтаксисе, используемом в этих конструкциях, обратитесь к документации для каждой языковой конструкции.</span><span class="sxs-lookup"><span data-stu-id="bc1cd-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="bc1cd-115">Конструкция языка</span><span class="sxs-lookup"><span data-stu-id="bc1cd-115">Language construct</span></span></th>
<th><span data-ttu-id="bc1cd-116">Легкий синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc1cd-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="bc1cd-117">Многословный синтаксис</span><span class="sxs-lookup"><span data-stu-id="bc1cd-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="bc1cd-118">сложные выражения</span><span class="sxs-lookup"><span data-stu-id="bc1cd-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1 />
<expression2 />
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="bc1cd-119">вложенные `let` привязки</span><span class="sxs-lookup"><span data-stu-id="bc1cd-119">nested `let` bindings</span></span>

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
<span data-ttu-id="bc1cd-120">кодовый блок</span><span class="sxs-lookup"><span data-stu-id="bc1cd-120">code block</span></span>
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```

</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```fsharp
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-121">запись</span><span class="sxs-lookup"><span data-stu-id="bc1cd-121">record</span></span>
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-122">class</span><span class="sxs-lookup"><span data-stu-id="bc1cd-122">class</span></span>
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-123">structure</span><span class="sxs-lookup"><span data-stu-id="bc1cd-123">structure</span></span></td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-124">дискриминированный союз</span><span class="sxs-lookup"><span data-stu-id="bc1cd-124">discriminated union</span></span></td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-125">interface</span><span class="sxs-lookup"><span data-stu-id="bc1cd-125">interface</span></span></td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-126">выражение объекта</span><span class="sxs-lookup"><span data-stu-id="bc1cd-126">object expression</span></span></td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-127">реализация интерфейсов</span><span class="sxs-lookup"><span data-stu-id="bc1cd-127">interface implementation</span></span></td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-128">расширение типа</span><span class="sxs-lookup"><span data-stu-id="bc1cd-128">type extension</span></span></td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td><span data-ttu-id="bc1cd-129">module</span><span class="sxs-lookup"><span data-stu-id="bc1cd-129">module</span></span></td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a><span data-ttu-id="bc1cd-130">См. также</span><span class="sxs-lookup"><span data-stu-id="bc1cd-130">See also</span></span>

- [<span data-ttu-id="bc1cd-131">Ссылка на язык F</span><span class="sxs-lookup"><span data-stu-id="bc1cd-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bc1cd-132">Директивы компилятора</span><span class="sxs-lookup"><span data-stu-id="bc1cd-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="bc1cd-133">Рекомендации по форматированию кода</span><span class="sxs-lookup"><span data-stu-id="bc1cd-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
