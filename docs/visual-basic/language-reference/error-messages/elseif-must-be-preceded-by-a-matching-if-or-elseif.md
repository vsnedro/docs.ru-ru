---
title: 'Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 06af269508db6a2b258251272fdc18ef20eb1c0f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874441"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf

`#ElseIf` является директивой условной компиляции. `#ElseIf`Оператору должно предшествовать соответствующее `#If` `#ElseIf` предложение или.  
  
 **Идентификатор ошибки:** BC30014  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что предыдущий `#If` или `#ElseIf` не был отделен от него `#ElseIf` промежуточным блоком условной компиляции или неправильно размещен `#End If` .  
  
2. Если `#ElseIf` перед `#Else` директивой стоит либо удалить, `#Else` либо изменить ее на `#ElseIf` .  
  
3. Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.  
  
## <a name="see-also"></a>См. также

- [Директивы #If...Then...#Else](../directives/if-then-else-directives.md)
