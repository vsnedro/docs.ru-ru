---
title: 'Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf'
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 808cf35fb05da092cdef560721b2f667778aa78f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409664"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>Оператору #ElseIf должен предшествовать соответствующий оператор #If или #ElseIf
`#ElseIf` является директивой условной компиляции. `#ElseIf`Оператору должно предшествовать соответствующее `#If` `#ElseIf` предложение или.  
  
 **Идентификатор ошибки:** BC30014  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Убедитесь, что предыдущий `#If` или `#ElseIf` не был отделен от него `#ElseIf` промежуточным блоком условной компиляции или неправильно размещен `#End If` .  
  
2. Если `#ElseIf` перед `#Else` директивой стоит либо удалить, `#Else` либо изменить ее на `#ElseIf` .  
  
3. Если все остальное в порядке, добавьте директиву `#If` в начало блока условной компиляции.  
  
## <a name="see-also"></a>См. также раздел

- [Директивы #If...Then...#Else](../directives/if-then-else-directives.md)
