---
title: Операнд IsNot типа  можно сравнить только с Nothing, так как  является типом, допускающим значение NULL
ms.date: 07/20/2015
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords:
- BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
ms.openlocfilehash: fb61b04021bd844fade94413b4f3b28b82f6411b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402802"
---
# <a name="isnot-operand-of-type-typename-can-only-be-compared-to-nothing-because-typename-is-a-nullable-type"></a>Операнд IsNot типа  можно сравнить только с Nothing, так как  является типом, допускающим значение NULL

Переменная, объявленная как тип значения, допускающего значение null, была сравнена с выражением, отличным от `Nothing` `IsNot` оператора.

**Идентификатор ошибки:** BC32128

## <a name="to-correct-this-error"></a>Исправление ошибки

Чтобы сравнить тип, допускающий значение null, с выражением, отличным от `Nothing` , с помощью оператора `IsNot` , вызовите метод `GetType` для типа, допускающего значение null, и сравните результат с выражением, как показано в следующем примере.

```vb
Dim number? As Integer = 5

If number IsNot Nothing Then
  If number.GetType() IsNot Type.GetType("System.Int32") Then

  End If
End If
```

## <a name="see-also"></a>См. также раздел

- [Типы значений, допускающие значение null](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Оператор IsNot](../operators/isnot-operator.md)
