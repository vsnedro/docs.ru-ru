---
description: Дополнительные сведения о инструкции Continue (Visual Basic)
title: Оператор Continue
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: c6d67e766b2551956795803076efe639ba3c8c99
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673873"
---
# <a name="continue-statement-visual-basic"></a>Оператор Continue (Visual Basic)

Немедленно передает управление следующей итерации цикла.  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Remarks  

 Можно переносить из `Do` `For` цикла, или `While` в следующую итерацию этого цикла. Элемент управления сразу же передается в условие цикла, что эквивалентно передаче `For` инструкции или или `While` `Do` `Loop` инструкции или, содержащей `Until` `While` предложение OR.  
  
 Можно использовать `Continue` в любом расположении в цикле, допускающем передачу данных. Правила, допускающие перемещение элементов управления, аналогичны [инструкциям оператора goto](goto-statement.md).  
  
 Например, если цикл полностью содержится в `Try` блоке, `Catch` блоке или `Finally` блоке, можно использовать `Continue` для перемещения цикла. Если, с другой стороны, `Try` структура... `End Try` содержится в цикле, нельзя использовать `Continue` для передачи управления из `Finally` блока, и ее можно использовать для передачи из `Try` блока или только в том `Catch` случае, если полностью передать из `Try` структуры... `End Try` .  
  
 При наличии вложенных циклов одного и того же типа, например `Do` цикла в другом `Do` цикле, `Continue Do` оператор переходит к следующей итерации самого внутреннего `Do` цикла, который его содержит. Нельзя использовать `Continue` для перехода к следующей итерации содержащего цикла того же типа.  
  
 При наличии вложенных циклов разных типов, например цикла в `Do` `For` цикле, можно перейти к следующей итерации любого цикла, используя либо `Continue Do` или `Continue For` .  
  
## <a name="example"></a>Пример  

 В следующем примере кода инструкция используется `Continue While` для перехода к следующему столбцу массива, если делитель равен нулю. `Continue While`Находится внутри `For` цикла. Он передает `While col < lastcol` оператору, который является следующей итерацией самого внутреннего `While` цикла, содержащего `For` цикл.  
  
 [!code-vb[VbVbalrStatements#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#14)]  
  
## <a name="see-also"></a>См. также

- [Оператор Do…Loop](do-loop-statement.md)
- [Оператор For…Next](for-next-statement.md)
- [Оператор While…End While](while-end-while-statement.md)
- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
