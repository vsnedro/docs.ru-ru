---
title: Циклические структуры
ms.date: 07/20/2015
helpviewer_keywords:
- control flow [Visual Basic], loops
- For keyword [Visual Basic], loop structures
- loops
- loop structures [Visual Basic]
- statements [Visual Basic], loop
- Do statement [Visual Basic], Do loops
- conditional statements [Visual Basic], loop structures
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
ms.openlocfilehash: 5019eaf219ad70f9c667356636d05ab69fc5a187
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077219"
---
# <a name="loop-structures-visual-basic"></a>Циклические структуры (Visual Basic)

Структуры циклов Visual Basic позволяют многократно выполнять одну или несколько строк кода. Операторы можно повторять в структуре цикла, пока условие не будет равно, `True` пока условие не будет равно `False` , заданное число раз или один раз для каждого элемента в коллекции.  
  
 На следующем рисунке показана структура цикла, выполняющая набор инструкций, пока условие не примет значение true:  
  
 ![Блок-схема, на которой показано действие Do... Цикл Until.](./media/loop-structures/do-until-loop-true-condition.gif)  
  
## <a name="while-loops"></a>Циклы while  

 `While`Конструкция... `End While` выполняет набор инструкций, пока условие, заданное в `While` инструкции, имеет значение `True` . Дополнительные сведения см. в разделе [while... Конец оператора while](../../../language-reference/statements/while-end-while-statement.md).  
  
## <a name="do-loops"></a>Do Loops  

 `Do`Конструкция... `Loop` позволяет проверить условие в начале или в конце структуры цикла. Можно также указать, следует ли повторять цикл, пока условие остается, `True` или пока не станет `True` . Дополнительные сведения см. в разделе [Do... Loop, инструкция](../../../language-reference/statements/do-loop-statement.md).  
  
## <a name="for-loops"></a>Циклы for  

 `For`Конструкция... `Next` выполняет цикл в заданное число раз. Для наблюдения за повторениями используется управляющая переменная цикла, также называемая *счетчиком*. Вы указываете начальное и конечное значения для этого счетчика, а также можете указать величину, на которую увеличивается от одного повтора до следующего. Дополнительные сведения см. в разделе [for... Следующий оператор](../../../language-reference/statements/for-next-statement.md).  
  
## <a name="for-each-loops"></a>Циклы for each  

 `For Each`Конструкция... `Next` выполняет набор инструкций один раз для каждого элемента в коллекции. Вы указываете управляющую переменную цикла, но не нужно определять начальные или конечные значения для нее. Дополнительные сведения см. в разделе [For Each... Следующий оператор](../../../language-reference/statements/for-each-next-statement.md).  
  
## <a name="see-also"></a>См. также

- [Поток управления](index.md)
- [Структуры решений](decision-structures.md)
- [Другие структуры управления](other-control-structures.md)
- [Вложенные структуры управления](nested-control-structures.md)
