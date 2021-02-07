---
description: 'Дополнительные сведения о операторе: is (Visual Basic)'
title: Оператор is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 0912ebd9bc9c33149568c6cea0197ef24c305ff2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665689"
---
# <a name="is-operator-visual-basic"></a>Оператор is (Visual Basic)

Сравнивает две переменные ссылки на объект.

## <a name="syntax"></a>Синтаксис

```vb
result = object1 Is object2
```

## <a name="parts"></a>Компоненты

 `result`  
 Обязательный элемент. Любое `Boolean` значение.  
  
 `object1`  
 Обязательный элемент. Любое `Object` имя.  
  
 `object2`  
 Обязательный элемент. Любое `Object` имя.  
  
## <a name="remarks"></a>Remarks

`Is`Оператор определяет, ссылаются ли две объектные ссылки на один и тот же объект. Однако сравнение значений не выполняется. Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` имеет значение `True` ; Если нет, `result` то имеет значение `False` .

> [!NOTE]
> `Is`Ключевое слово также используется в [SELECT... Case, инструкция](../statements/select-case-statement.md).
  
## <a name="example"></a>Пример

В следующем примере оператор используется `Is` для сравнения пар ссылок на объекты. Результаты присваиваются `Boolean` значению, представляющему идентичность двух объектов.

[!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]

Как показано в предыдущем примере, оператор можно использовать `Is` для тестирования объектов с ранней и поздней привязкой.

## <a name="use-typeof-operator-with-is-operator"></a>Использование оператора TypeOf с оператором is

`Is` Оператор также можно использовать с `TypeOf` ключевым словом для создания `TypeOf` выражения... `Is` , которое проверяет, совместима ли объектная переменная с типом данных. Пример:

```vb
If TypeOf sender Is Button Then
```

## <a name="see-also"></a>См. также

- [Оператор TypeOf](typeof-operator.md)
- [Оператор IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы и выражения](../../programming-guide/language-features/operators-and-expressions/index.md)
