---
description: 'Дополнительные сведения о операторе: ^ (Visual Basic)'
title: Оператор ^
ms.date: 07/20/2015
f1_keywords:
- vb.^
helpviewer_keywords:
- raising numbers to powers
- ^ operator [Visual Basic], exponentiation
- square operator [Visual Basic]
- ^ operator [Visual Basic]
- exponentiation operator [Visual Basic]
- exponent
- numbers [Visual Basic], rasing
- powers
- arithmetic operators [Visual Basic], exponentiation
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
ms.openlocfilehash: 9333eec7236c363417be7323b673231509da8f1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666047"
---
# <a name="-operator-visual-basic"></a>Оператор ^ (Visual Basic)

Возводит число в степень другого числа.

## <a name="syntax"></a>Синтаксис

```vb
number ^ exponent
```

## <a name="parts"></a>Компоненты

`number`\
Обязательный. Произвольное числовое выражение.

`exponent`\
Обязательный. Произвольное числовое выражение.

## <a name="result"></a>Результат

Результат возводится в `number` степень `exponent` , всегда как `Double` значение.

## <a name="supported-types"></a>Поддерживаемые типы

`Double`. Операнды любого другого типа преобразуются в `Double` .

## <a name="remarks"></a>Remarks

Visual Basic всегда выполняет возведение в степень в [типе данных Double](../data-types/double-data-type.md).

Значение `exponent` может быть дробным, отрицательным или обоими.

Если в одном выражении выполняется несколько возможного возведения в степень, `^` оператор вычисляется так, как он встретился слева направо.

> [!NOTE]
> `^`Оператор можно *перегрузить*, что означает, что класс или структура может переопределить свое поведение, когда операнд имеет тип этого класса или структуры. Если код использует этот оператор для такого класса или структуры, убедитесь, что вы понимаете его переопределенное поведение. Для получения дополнительной информации см. [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

## <a name="example"></a>Пример

В следующем примере оператор используется `^` для возведения числа в степень экспоненты. Результатом является первый операнд, возведенный в степень второго.

[!code-vb[VbVbalrOperators#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#20)]

В предыдущем примере получены следующие результаты.

`exp1` имеет значение 4 (2 в квадрате).

`exp2` имеет значение 19683 (3 Куба, затем это значение Cube).

`exp3` имеет значение-125 (-5 кубd).

`exp4` имеет значение 625 (от-5 до четвертой мощности).

`exp5` имеет значение 2 (кубический корень из 8).

`exp6` имеет значение 0,5 (1,0, деленное на кубический корень из 8).

Обратите внимание на важность круглых скобок в выражениях из предыдущего примера. Из-за *приоритета операторов* Visual Basic обычно выполняет `^` оператор перед любыми другими, даже унарным `–` оператором. Если `exp4` и `exp6` были вычислены без скобок, они могли бы получить следующие результаты:

`exp4 = -5 ^ 4` будет вычисляться как – (от 5 до четвертой мощности), что приведет к появлению-625.

`exp6 = 8 ^ -1.0 / 3.0` вычисляется как (от 8 до – 1 или 0,125), деленное на 3,0, что приведет к 0.041666666666666666666666666666667.

## <a name="see-also"></a>См. также

- [Оператор ^ =](exponentiation-assignment-operator.md)
- [Арифметические операторы](arithmetic-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Арифметические операторы в Visual Basic](../../programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
