---
description: 'Дополнительные сведения: Функция CType (Visual Basic)'
title: CType Function
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 9732f52b40e5f762769ba5dc340c000e7e1ba17a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99701265"
---
# <a name="ctype-function-visual-basic"></a>Функция CType (Visual Basic)

Возвращает результат явного преобразования выражения в указанный тип данных, объект, структуру, класс или интерфейс.

## <a name="syntax"></a>Синтаксис

```vb
CType(expression, typename)
```

## <a name="parts"></a>Компоненты

`expression` Любое допустимое выражение. Если значение `expression` выходит за пределы диапазона, допустимого параметром `typename` , Visual Basic создает исключение.

`typename` Любое выражение, которое является допустимым в `As` предложении `Dim` оператора, то есть имя любого типа данных, объекта, структуры, класса или интерфейса.

## <a name="remarks"></a>Remarks

> [!TIP]
> Для преобразования типов также можно использовать следующие функции.
>
> - Функции преобразования типов, такие как `CByte` , `CDbl` и `CInt` , которые выполняют преобразование в конкретный тип данных. Дополнительные сведения см. в разделе [Функции преобразования типов](type-conversion-functions.md).
> - Оператор [DirectCast](../operators/directcast-operator.md) или [Оператор TryCast](../operators/trycast-operator.md). Для этих операторов требуется, чтобы один тип наследовал или реализовывал другой тип. Они могут обеспечить более высокую производительность, чем `CType` при преобразовании в тип данных и из него `Object` .

`CType` компилируется встроенным образом, что означает, что код преобразования является частью кода, который вычисляет выражение. В некоторых случаях код выполняется быстрее, так как для выполнения преобразования не вызываются никакие процедуры.

Если преобразование не определено из `expression` в `typename` (например, из в `Integer` `Date` ), Visual Basic отображает сообщение об ошибке времени компиляции.

Если во время выполнения происходит сбой преобразования, выдается соответствующее исключение. Если понижающие преобразования не удается выполнить, <xref:System.OverflowException> наиболее распространенным результатом является. Если преобразование не определено, <xref:System.InvalidCastException> в вызываемом элементе. Например, это может произойти, если `expression` имеет тип `Object` , а тип времени выполнения не имеет преобразования в `typename` .

Если тип данных `expression` или `typename` является определенным классом или структурой, можно определить `CType` в этом классе или структуре как оператор преобразования. Это делает работу `CType` в качестве *перегруженного оператора*. В этом случае можно управлять поведением преобразований в класс или структуру, включая исключения, которые могут быть созданы.

## <a name="overloading"></a>Перегрузка

`CType`Оператор также может быть перегружен для класса или структуры, определенной вне кода. Если код преобразует в или из такого класса или структуры, убедитесь, что вы понимаете поведение его `CType` оператора. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="converting-dynamic-objects"></a>Преобразование динамических объектов

Преобразования типов динамических объектов выполняются с помощью определяемых пользователем динамических преобразований, использующих <xref:System.Dynamic.DynamicObject.TryConvert%2A> <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> методы или. При работе с динамическими объектами используйте <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> метод для преобразования динамического объекта.

## <a name="example"></a>Пример

В следующем примере функция используется `CType` для преобразования выражения в `Single` тип данных.

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

Дополнительные примеры см. в разделе [явные и неявные преобразования](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).

## <a name="see-also"></a>См. также

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [Type Conversion Functions](type-conversion-functions.md)
- [Функции преобразования](conversion-functions.md)
- [Operator Statement](../statements/operator-statement.md)
- [Практическое руководство. Определение оператора преобразования](../../programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [Преобразование типов в .NET Framework](../../../standard/base-types/type-conversion.md)
