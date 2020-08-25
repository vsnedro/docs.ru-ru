---
title: IsNot - оператор
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- comparison operators [Visual Basic]
- TypeOf...IsNot expression
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: ea978f8874cee20fb3a005189fd846f7564da777
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811045"
---
# <a name="isnot-operator-visual-basic"></a>Оператор IsNot (Visual Basic)

Сравнивает две переменные ссылки на объект.

## <a name="syntax"></a>Синтаксис

```vb
result = object1 IsNot object2
```

## <a name="parts"></a>Компоненты

- `result`

  Обязательный. Значение `Boolean`.

- `object1`

  Обязательный. Любая `Object` переменная или выражение.

- `object2`

  Обязательный. Любая `Object` переменная или выражение.

## <a name="remarks"></a>Комментарии

`IsNot`Оператор определяет, ссылаются ли две объектные ссылки на разные объекты. Однако сравнение значений не выполняется. Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` имеет значение `False` ; Если нет, `result` то имеет значение `True` .

`IsNot` является противоположностью `Is` оператора. Преимущество заключается в том `IsNot` , что можно избежать неудобного синтаксиса с `Not` и `Is` , что может быть трудно читать.

 Операторы и можно использовать `Is` `IsNot` для тестирования объектов с ранней и поздней привязкой.

## <a name="example"></a>Пример

В следующем примере кода используются `Is` оператор и `IsNot` оператор для выполнения одинакового сравнения.

[!code-vb[VbVbalrOperators#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#29)]

## <a name="use-typeof-operator-with-isnot-operator"></a>Использование оператора TypeOf с оператором IsNot

Начиная с Visual Basic 14 можно использовать `TypeOf` оператор с `IsNot` оператором, чтобы проверить, несовместим ли объект с типом *not* данных. Пример:

```vb
If TypeOf sender IsNot Button Then
```

## <a name="see-also"></a>См. также

- [Оператор is](is-operator.md)
- [TypeOf, оператор](typeof-operator.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Практическое руководство. Проверка совпадения двух объектов](../../programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
