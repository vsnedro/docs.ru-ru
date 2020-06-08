---
title: Руководство по программированию на C#. Буферы фиксированного размера
ms.date: 04/23/2020
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 932ff3d57995ce47c4b74e8e888a479f0d09d0ed
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397432"
---
# <a name="fixed-size-buffers-c-programming-guide"></a>Буферы фиксированного размера (Руководство по программированию на C#)

В языке C# для создания буфера с массивом фиксированного размера в структуре данных можно использовать оператор [fixed](../../language-reference/keywords/fixed-statement.md). Буферы фиксированного размера полезны при написании методов, взаимодействующих с источниками данных, созданными на других языках или платформах. Фиксированный массив может принимать любые атрибуты или модификаторы, допустимые для обычных членов структуры. Единственным ограничением является то, что массив должен иметь тип `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` или `double`.

```csharp
private fixed char name[30];
```

## <a name="remarks"></a>Примечания

В безопасном коде структура C#, содержащая массив, не содержит элементы массива. Вместо этого в ней присутствуют ссылки на элементы. Вы можете внедрить массив фиксированного размера в [структуру](../../language-reference/builtin-types/struct.md), если он используется в блоке [небезопасного](../../language-reference/keywords/unsafe.md) кода.

Размер следующего объекта `struct` не зависит от количества элементов в массиве, поскольку `pathName` представляет собой ссылку:

[!code-csharp[Struct with embedded array](snippets/FixedKeywordExamples.cs#6)]

`struct` может содержать внедренный массив в небезопасном коде. В приведенном ниже примере массив `fixedBuffer` имеет фиксированный размер. Для установки указателя на первый элемент используется оператор `fixed`. С помощью этого указателя осуществляется доступ к элементам массива. Оператор `fixed` закрепляет поле экземпляра `fixedBuffer` в определенном месте в памяти.

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#7)]

Размер массива из 128 элементов `char` составляет 256 байт. В буферах типа [char](../../language-reference/builtin-types/char.md) фиксированного размера на один символ всегда приходится два байта независимо от кодировки. Это справедливо даже в том случае, когда буферы char маршалируются в методы API или структуры с `CharSet = CharSet.Auto` или `CharSet = CharSet.Ansi`. Для получения дополнительной информации см. <xref:System.Runtime.InteropServices.CharSet>.

В предыдущем примере демонстрировался доступ к полям `fixed` без закрепления в памяти, доступный в C#, начиная с версии 7.3.

Еще одним распространенным массивом фиксированного размера является массив [bool](../../language-reference/builtin-types/bool.md). Элементы в массиве `bool` всегда имеют размер в один байт. Массивы `bool` не подходят для создания битовых массивов или буферов.

Буферы фиксированного размера компилируются с помощью класса <xref:System.Runtime.CompilerServices.UnsafeValueTypeAttribute?displayProperty=nameWithType>, что указывает среде CLR, что тип содержит неуправляемый массив, который может привести к переполнению. Это похоже на память, созданную с помощью [stackalloc](../../language-reference/operators/stackalloc.md), которая автоматически включает функции обнаружения переполнения буфера в среде CLR. В предыдущем примере показано существование буфера фиксированного размера в `unsafe struct`.

```csharp
internal unsafe struct Buffer
{
    public fixed char fixedBuffer[128];
}
```

Созданный компилятором код C# для `Buffer` помечен с помощью атрибутов, как показано далее.

```csharp
internal struct Buffer
{
    [StructLayout(LayoutKind.Sequential, Size = 256)]
    [CompilerGenerated]
    [UnsafeValueType]
    public struct <fixedBuffer>e__FixedBuffer
    {
        public char FixedElementField;
    }

    [FixedBuffer(typeof(char), 128)]
    public <fixedBuffer>e__FixedBuffer fixedBuffer;
}
```

Буферы фиксированного размера отличаются от обычных массивов указанными ниже особенностями.

- Могут использоваться только в [небезопасном](../../language-reference/keywords/unsafe.md) контексте.
- Могут быть только полями экземпляров структур.
- Всегда являются векторами или одномерными массивами.
- Объявление должно включать длину, например `fixed char id[8]`. Использовать `fixed char id[]` нельзя.

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [Небезопасный код и указатели](index.md)
- [Оператор fixed](../../language-reference/keywords/fixed-statement.md)
- [Взаимодействие](../interop/index.md)
