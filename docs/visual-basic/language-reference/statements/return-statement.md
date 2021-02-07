---
description: 'Дополнительные сведения: оператор return (Visual Basic)'
title: Оператор Return
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: 62086090ede7e634b09d3edc3dc42feb28d15793
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741202"
---
# <a name="return-statement-visual-basic"></a>Оператор Return (Visual Basic)

Возвращает управление коду, который вызвал `Function` процедуру,, `Sub` `Get` , `Set` или `Operator` .  
  
## <a name="syntax"></a>Синтаксис  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Отделение  

 `expression`  
 Требуется в `Function` процедуре, `Get` или `Operator` . Выражение, представляющее значение, возвращаемое вызывающему коду.  
  
## <a name="remarks"></a>Remarks  

 В `Sub` процедуре или `Set` `Return` инструкция эквивалентна `Exit Sub` `Exit Property` оператору или и `expression` не должна быть указана.  
  
 В `Function` процедуре, `Get` или `Operator` `Return` инструкция должна включать оператор `expression` и `expression` должен иметь тип данных, преобразуемый в возвращаемый тип процедуры. В `Function` процедуре или `Get` вы также можете назначить выражение имени процедуры, которое будет использоваться в качестве возвращаемого значения, а затем выполнить `Exit Function` `Exit Property` инструкцию или. В `Operator` процедуре необходимо использовать `Return expression` .  
  
 В одной процедуре можно включить столько инструкций, сколько `Return` необходимо.  
  
> [!NOTE]
> Код в `Finally` блоке выполняется после `Return` обнаружения оператора в `Try` `Catch` блоке или, но перед `Return` выполнением этой инструкции. `Return`Инструкция не может быть включена в `Finally` блок.  
  
## <a name="example"></a>Пример  

 В следующем примере оператор используется `Return` несколько раз для возврата к вызывающему коду, если процедура не должна предпринимать никаких других действий.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>См. также

- [Оператор Function](function-statement.md)
- [Оператор Sub](sub-statement.md)
- [Оператор Get](get-statement.md)
- [Инструкция SET](set-statement.md)
- [Operator Statement](operator-statement.md)
- [Property Statement](property-statement.md)
- [Оператор Exit](exit-statement.md)
- [Оператор Try...Catch...Finally](try-catch-finally-statement.md)
