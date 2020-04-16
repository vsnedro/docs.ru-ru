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
# <a name="verbose-syntax"></a>Подробный синтаксис

Для многих конструкций на языке F-образного языка доступны две формы синтаксиса: *многословный синтаксис* и *легкий синтаксис.* Многословный синтаксис не так часто используется, но имеет то преимущество, что менее чувствителен к отступам. Легкий синтаксис короче и использует отступы для сигнала начала и конца `begin`конструкций, а не дополнительные ключевые слова, как , `end`, `in`и так далее. Синтаксис по умолчанию — это легкий синтаксис. В этой теме описывается синтаксис для конструкций F-из, когда легкий синтаксис не включен. Синтеза Verbose всегда включен, так что даже если вы включите легкий синтаксис, вы все равно можете использовать многословный синтаксис для некоторых конструкций. Можно отключить легкий синтаксис `#light "off"` с помощью директивы.

## <a name="table-of-constructs"></a>Таблица конструкций

В следующей таблице показан легкий и многословный синтаксис для языковых конструкций f в контекстах, где есть разница между этими двумя формами. В этой таблице угловые скобки ()&lt;&gt;прилагают элементы синтаксиса, поставляемого пользователем. Для получения более подробной информации о синтаксисе, используемом в этих конструкциях, обратитесь к документации для каждой языковой конструкции.

<table>
<tr>
<th>Конструкция языка</th>
<th>Легкий синтаксис</th>
<th>Многословный синтаксис</th>
</tr>
<tr>
<td>
сложные выражения
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

вложенные `let` привязки

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
кодовый блок
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
<tr><td>запись
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
<tr><td>class
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
<tr><td>structure</td><td>

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
<tr><td>дискриминированный союз</td><td>

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
<tr><td>interface</td><td>

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
<tr><td>выражение объекта</td><td>

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
<tr><td>реализация интерфейсов</td><td>

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
<tr><td>расширение типа</td><td>

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
<tr><td>module</td><td>

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

## <a name="see-also"></a>См. также

- [Ссылка на язык F](index.md)
- [Директивы компилятора](compiler-directives.md)
- [Рекомендации по форматированию кода](../style-guide/formatting.md)
