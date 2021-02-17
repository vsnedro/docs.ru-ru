---
title: Синтаксис, используемый свойством DebugView
description: В этой статье описывается специальный синтаксис, используемый свойством DebugView для получения строкового представления деревьев выражений.
author: zspitz
ms.author: wiwagn
ms.date: 14/02/2021
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 8a4feac72c2cd79485f5733b16d65b52cc50ee6c
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584888"
---
# <a name="debugview-syntax"></a>Синтаксис **DebugView**

Свойство **DebugView** (доступно только при отладке) обеспечивает отрисовку строк деревьев выражений. Большая часть синтаксиса достаточно проста для понимания; особые случаи описаны в разделах ниже.

За каждым примером следует блок комментариев, содержащий **DebugView**.

## <a name="parameterexpression"></a>ParameterExpression

В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".

Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.

### <a name="examples"></a>Примеры

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a>ConstantExpressions

Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.

Для некоторых числовых типов суффикс добавляется к значению:

| Type | Ключевое слово | Суффикс |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [UInteger](../../../language-reference/data-types/uinteger-data-type.md) | U |
| <xref:System.Int64?displayProperty=nameWithType> | [Long](../../../language-reference/data-types/long-data-type.md) | L |
| <xref:System.UInt64?displayProperty=nameWithType> | [ULong](../../../language-reference/data-types/ulong-data-type.md) | UL |
| <xref:System.Double?displayProperty=nameWithType> | [Double](../../../language-reference/data-types/double-data-type.md) | D |
| <xref:System.Single?displayProperty=nameWithType> | [Single](../../../language-reference/data-types/single-data-type.md) | F |
| <xref:System.Decimal?displayProperty=nameWithType> | [Десятичное число](../../../language-reference/data-types/decimal-data-type.md) | M |

### <a name="examples"></a>Примеры

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a>BlockExpression

Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в угловых скобках (`<` и `>`). В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.

### <a name="examples"></a>Примеры

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object),
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a>LambdaExpression

Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.

Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.

### <a name="examples"></a>Примеры

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a>LabelExpression

Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.

Маркер `.Label` указывает начало метки. Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.

Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.

### <a name="examples"></a>Примеры

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a>Проверяемые операторы

Проверяемые операторы отображаются с символом `#` перед оператором. Например, проверяемый оператор сложения отображается как `#+`.

### <a name="examples"></a>Примеры

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```
