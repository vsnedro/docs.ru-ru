---
description: 'Дополнительные сведения: типы значений, допускающие значение null (Visual Basic)'
title: Типы значений, допускающие значение NULL
ms.date: 07/20/2015
f1_keywords:
- vb.Nullable
helpviewer_keywords:
- nullable types [Visual Basic]
- '? [Visual Basic]'
- types [Visual Basic], nullable
- nullable types [Visual Basic]
- data types [Visual Basic], nullable
ms.assetid: 9ac3b602-6f96-4e6d-96f7-cd4e81c468a6
ms.openlocfilehash: acc91d98a3ed288a9bf0bcf6abbd3d8a516bd699
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483889"
---
# <a name="nullable-value-types-visual-basic"></a>Типы значения, допускающие Null (Visual Basic)

Иногда вы работаете с типом значения, который не имеет определенного значения в определенных обстоятельствах. Например, поле в базе данных может отличаться от присвоенного значения, которое является осмысленным и не имеет присвоенного значения. Типы значений могут быть расширены для получения их нормальных значений или значения NULL. Такое расширение называется *типом, допускающим значение NULL*.

Каждый тип значения, допускающий значение null, создается из универсальной <xref:System.Nullable%601> структуры. Рассмотрим базу данных, которая отслеживает действия, связанные с работой. В следующем примере создается тип, допускающий значение NULL `Boolean` , и объявляется переменная этого типа. Объявление можно написать тремя способами:

[!code-vb[VbVbalrNullableValue#1](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#1)]

Переменная `ridesBusToWork` может содержать значение `True` , значение `False` или вообще не иметь значения. Его начальное значение по умолчанию — вообще не имеет значения, что в данном случае может означать, что данные еще не были получены для этого пользователя. В отличие от этого, это `False` может означать, что информация получена и пользователь не передается на работу.

Можно объявить переменные и свойства с типами значений, допускающими значение null, и можно объявить массив с элементами типа значения, допускающего значение null. Можно объявлять процедуры с типами значений, допускающими значение null, в качестве параметров, а также возвращать тип значения, допускающий значение null, из `Function` процедуры.

Нельзя создать тип, допускающий значение null, для ссылочного типа, такого как массив, `String` или класс. Базовый тип должен быть типом значения. Дополнительные сведения см. в разделе [типы значений и ссылочные типы](value-types-and-reference-types.md).

## <a name="using-a-nullable-type-variable"></a>Использование переменной типа, допускающей значение null

Наиболее важными членами типа, допускающего значение null, являются <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> Свойства и. Для переменной типа значения, допускающего значение null, <xref:System.Nullable%601.HasValue%2A> сообщает, содержит ли переменная определенное значение. Если <xref:System.Nullable%601.HasValue%2A> параметр имеет `True` значение, то можно считать значения из <xref:System.Nullable%601.Value%2A> . Обратите внимание, что <xref:System.Nullable%601.HasValue%2A> <xref:System.Nullable%601.Value%2A> Свойства и являются `ReadOnly` свойствами.

### <a name="default-values"></a>Значения по умолчанию

При объявлении переменной с типом значения, допускающим значение null, ее <xref:System.Nullable%601.HasValue%2A> свойство имеет значение по умолчанию `False` . Это означает, что по умолчанию переменная не имеет определенного значения, а не значения по умолчанию базового типа значения. В следующем примере переменная `numberOfChildren` изначально не имеет определенного значения, хотя значение по умолчанию для этого `Integer` типа равно 0.

[!code-vb[VbVbalrNullableValue#2](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#2)]

Значение NULL полезно для указания неопределенного или неизвестного значения. Если было `numberOfChildren` объявлено как `Integer` , то не будет значения, которое может указывать на то, что информация в настоящее время недоступна.

### <a name="storing-values"></a>Сохранение значений

Вы сохраняете значение в переменной или свойстве типа значения, допускающего значение null, обычным способом. В следующем примере значение присваивается переменной, `numberOfChildren` объявленной в предыдущем примере.

[!code-vb[VbVbalrNullableValue#3](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#3)]

Если переменная или свойство типа значения, допускающего значение null, содержит определенное значение, можно вернуть его первоначальное состояние, не имеющее присвоенного значения. Для этого нужно задать для переменной или свойства значение `Nothing` , как показано в следующем примере.

[!code-vb[VbVbalrNullableValue#4](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#4)]

> [!NOTE]
> Хотя можно присвоить `Nothing` переменной тип значения, допускающего значение null, его нельзя проверить с `Nothing` помощью знака равенства. При сравнении, в котором используется знак равенства, `someVar = Nothing` всегда вычисляется значение `Nothing` . Можно проверить <xref:System.Nullable%601.HasValue%2A> свойство переменной для `False` или проверить с помощью `Is` `IsNot` оператора или.

### <a name="retrieving-values"></a>Получение значений

Чтобы получить значение переменной типа, допускающего значение null, сначала следует проверить его <xref:System.Nullable%601.HasValue%2A> свойство, чтобы убедиться, что оно имеет значение. Если вы попытаетесь считать значение <xref:System.Nullable%601.HasValue%2A> , то `False` Visual Basic создает <xref:System.InvalidOperationException> исключение. В следующем примере показан рекомендуемый способ чтения переменной `numberOfChildren` из предыдущих примеров.

[!code-vb[VbVbalrNullableValue#5](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#5)]

## <a name="comparing-nullable-types"></a>Сравнение типов, допускающих значение null

Если `Boolean` в логических выражениях используются допускающие значения NULL переменные, результатом может быть `True` , `False` или `Nothing` . Ниже приведена таблица истинности для `And` и `Or` . Поскольку `b1` `b2` у и теперь есть три возможных значения, можно вычислить девять комбинаций.

|B1|ячейк|B1 и B2|B1 или B2|
|--------|--------|---------------|--------------|
|`Nothing`|`Nothing`|`Nothing`|`Nothing`|
|`Nothing`|`True`|`Nothing`|`True`|
|`Nothing`|`False`|`False`|`Nothing`|
|`True`|`Nothing`|`Nothing`|`True`|
|`True`|`True`|`True`|`True`|
|`True`|`False`|`False`|`True`|
|`False`|`Nothing`|`False`|`Nothing`|
|`False`|`True`|`False`|`True`|
|`False`|`False`|`False`|`False`|

Если значение логической переменной или выражения равно `Nothing` , то оно не равно ни `true` `false` . Рассмотрим следующий пример.

[!code-vb[VbVbalrNullableValue#6](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#6)]

В этом примере `b1 And b2` принимает значение `Nothing` . В результате `Else` предложение выполняется в каждой `If` инструкции, и выходные данные выглядят следующим образом:

`Expression is not true`

`Expression is not false`

> [!NOTE]
> `AndAlso` и `OrElse` , использующие сокращенную оценку, должны оценивать свои вторые операнды при первом вычислении до `Nothing` .

## <a name="propagation"></a>Распространение

Если один или оба операнда арифметических операций, операции сравнения, сдвига или типа имеют тип значения, допускающий значение null, результат операции также является типом значения, допускающим значение null. Если оба операнда имеют значения, которые не являются `Nothing` , операция выполняется с базовыми значениями операндов, как если бы ни был тип значения, допускающий значение null. В следующем примере переменные `compare1` и `sum1` неявно типизированы. Если навести на них указатель мыши, вы увидите, что компилятор определит типы значений, допускающие значение null, для обоих типов.

[!code-vb[VbVbalrNullableValue#7](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#7)]

Если один или оба операнда имеют значение `Nothing` , результатом будет `Nothing` .

[!code-vb[VbVbalrNullableValue#8](../../../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrNullableValue/VB/Class1.vb#8)]

## <a name="using-nullable-types-with-data"></a>Использование типов, допускающих значение null, с данными

База данных является одним из наиболее важных мест для использования типов значений, допускающих значение null. Не все объекты базы данных в настоящее время поддерживают типы значений, допускающие значения NULL, но адаптеры таблиц, созданные конструктором, выполняют. См. раздел [Поддержка TableAdapter для типов, допускающих значение NULL](/visualstudio/data-tools/fill-datasets-by-using-tableadapters#tableadapter-support-for-nullable-types).

## <a name="see-also"></a>См. также раздел

- <xref:System.InvalidOperationException>
- <xref:System.Nullable%601.HasValue%2A>
- [Типы данных](index.md)
- [Value Types and Reference Types](value-types-and-reference-types.md)
- [Устранение неполадок, связанных с типами данных](troubleshooting-data-types.md)
- [Заполнение наборов данных с помощью адаптеров таблицы](/visualstudio/data-tools/fill-datasets-by-using-tableadapters)
- [Оператор If](../../../language-reference/operators/if-operator.md)
- [Вывод локального типа](../variables/local-type-inference.md)
- [Оператор Is](../../../language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../language-reference/operators/isnot-operator.md)
- [Типы значений, допускающие значение null (C#)](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)
