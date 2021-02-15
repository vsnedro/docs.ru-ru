---
description: Дополнительные сведения см. в статье как определить идентичность двух объектов (Visual Basic)
title: Практическое руководство. Определение идентичности двух объектов
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: 91f431b5a7e4cf51135c060ca0aebf1b3b968b25
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481900"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Практическое руководство. Определение идентичности двух объектов (Visual Basic)

В Visual Basic две ссылки на переменные считаются идентичными, если их указатели одинаковы, то есть если обе переменные указывают на один и тот же экземпляр класса в памяти. Например, в Windows Forms приложении может потребоваться выполнить сравнение, чтобы определить, совпадает ли текущий экземпляр ( `Me` ) с конкретным экземпляром, например `Form2` .  
  
 Visual Basic предоставляет два оператора для сравнения указателей. [Оператор is](../../../language-reference/operators/is-operator.md) возвращает значение `True` , если объекты идентичны, и [оператор IsNot](../../../language-reference/operators/isnot-operator.md) возвращает значение, `True` если это не так.  
  
## <a name="determining-if-two-objects-are-identical"></a>Определение идентичности двух объектов  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Определение идентичности двух объектов  
  
1. Настройте `Boolean` выражение для проверки двух объектов.  
  
2. В тестовом выражении используйте `Is` оператор с двумя объектами в качестве операндов.  
  
     `Is` Возвращает значение `True` , если объекты указывают на один и тот же экземпляр класса.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Определение того, что два объекта не идентичны  

 Иногда требуется выполнить действие, если эти два объекта не идентичны, и, например, могут быть неудобными для объединения `Not` и `Is` `If Not obj1 Is obj2` . В этом случае можно использовать `IsNot` оператор.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Определение того, что два объекта не идентичны  
  
1. Настройте `Boolean` выражение для проверки двух объектов.  
  
2. В тестовом выражении используйте `IsNot` оператор с двумя объектами в качестве операндов.  
  
     `IsNot` Возвращает значение `True` , если объекты не указывают на один и тот же экземпляр класса.  
  
## <a name="example"></a>Пример  

 В следующем примере показано `Object` , как проверить пары переменных, чтобы определить, указывают ли они на один и тот же экземпляр класса.  
  
 [!code-vb[VbVbalrKeywords#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#14)]  
  
 В предыдущем примере отображаются следующие выходные данные.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>См. также раздел

- [Object Data Type](../../../language-reference/data-types/object-data-type.md)
- [Объектные переменные](object-variables.md)
- [Значения объектных переменных](object-variable-values.md)
- [Оператор Is](../../../language-reference/operators/is-operator.md)
- [Оператор IsNot](../../../language-reference/operators/isnot-operator.md)
- [Практическое руководство. Определение наличия связи между двумя объектами](how-to-determine-whether-two-objects-are-related.md)
- [Me, My, MyBase и MyClass](../../program-structure/me-my-mybase-and-myclass.md)
