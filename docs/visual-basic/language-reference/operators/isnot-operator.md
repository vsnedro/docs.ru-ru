---
description: 'Дополнительные сведения: оператор IsNot (Visual Basic)'
title: IsNot - оператор
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ac3e127676dfa57d14e07838152022de62fc336b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665670"
---
# <a name="isnot-operator-visual-basic"></a>Оператор IsNot (Visual Basic)

Сравнивает две переменные ссылки на объект.

## <a name="syntax"></a>Синтаксис

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Компоненты

- `result`

  Обязательный элемент. Значение `Boolean`.

- `object1`

  Обязательный элемент. Любая `Object` переменная или выражение.

- `object2`

  Обязательный элемент. Любая `Object` переменная или выражение.

## <a name="remarks"></a>Remarks

`IsNot`Оператор определяет, ссылаются ли две объектные ссылки на разные объекты. Однако сравнение значений не выполняется. Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` имеет значение `False` ; Если нет, `result` то имеет значение `True` .

`IsNot` является противоположностью `Is` оператора. Преимущество заключается в том `IsNot` , что можно избежать неудобного синтаксиса с `Not` и `Is` , что может быть трудно читать.

 Операторы и можно использовать `Is` `IsNot` для тестирования объектов с ранней и поздней привязкой.

## <a name="example"></a>Пример

В следующем примере кода используются `Is` оператор и `IsNot` оператор для выполнения одинакового сравнения.

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a>Использование оператора TypeOf с оператором IsNot

Начиная с Visual Basic 14 можно использовать `TypeOf` оператор с `IsNot` оператором, чтобы проверить, несовместим ли объект с типом  данных. Пример:

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a>См. также

- [Оператор Is](is-operator.md)
- [Оператор TypeOf](typeof-operator.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Практическое руководство. Проверка совпадения двух объектов](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
