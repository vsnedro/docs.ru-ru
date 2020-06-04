---
title: Оператор Is
ms.date: 07/20/2015
f1_keywords:
- vb.is
helpviewer_keywords:
- comparison operators [Visual Basic]
- equivalent objects
- TypeOf...Is expression
- Is operator [Visual Basic]
ms.assetid: 8045a6c8-2a83-45b6-ad47-d09a704c656d
ms.openlocfilehash: 3cc0ae5f04358fbe6b2aabc50498f39ca7225164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84370808"
---
# <a name="is-operator-visual-basic"></a>Оператор Is (Visual Basic)
Сравнивает две переменные ссылки на объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
result = object1 Is object2  
```  
  
## <a name="parts"></a>Компоненты  
 `result`  
 Обязательный. Любое `Boolean` значение.  
  
 `object1`  
 Обязательный. Любое `Object` имя.  
  
 `object2`  
 Обязательный. Любое `Object` имя.  
  
## <a name="remarks"></a>Комментарии  
 `Is`Оператор определяет, ссылаются ли две объектные ссылки на один и тот же объект. Однако сравнение значений не выполняется. Если `object1` и `object2` оба ссылаются на один и тот же экземпляр объекта, `result` имеет значение `True` ; Если нет, `result` то имеет значение `False` .  
  
 `Is`также можно использовать с `TypeOf` ключевым словом для создания `TypeOf` выражения... `Is` , которое проверяет, совместима ли объектная переменная с типом данных.  
  
> [!NOTE]
> `Is`Ключевое слово также используется в [SELECT... Case, инструкция](../statements/select-case-statement.md).  
  
## <a name="example"></a>Пример  
 В следующем примере оператор используется `Is` для сравнения пар ссылок на объекты. Результаты присваиваются `Boolean` значению, представляющему идентичность двух объектов.  
  
 [!code-vb[VbVbalrOperators#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#27)]  
  
 Как показано в предыдущем примере, оператор можно использовать `Is` для тестирования объектов с ранней и поздней привязкой.  
  
## <a name="see-also"></a>См. также раздел

- [TypeOf, оператор](typeof-operator.md)
- [Оператор IsNot](isnot-operator.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Порядок применения операторов в Visual Basic](operator-precedence.md)
- [Список операторов, сгруппированных по функциональному назначению](operators-listed-by-functionality.md)
- [Операторы и выражения](../../programming-guide/language-features/operators-and-expressions/index.md)
