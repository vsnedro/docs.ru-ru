---
title: Оператор не может завершить блок за пределами однострочной инструкции If
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 3fe3faaa3637446bb6ab443ba1d6e1d1004b4d48
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400322"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>Оператор не может завершить блок за пределами однострочной инструкции If
Однострочный `If` оператор содержит несколько операторов, разделенных двоеточиями (:), одна из которых является `End` оператором для блока управления за пределами однострочного `If` . Однострочные `If` операторы не используют `End If` инструкцию.  
  
 **Идентификатор ошибки:** BC32005  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Переместите однострочный `If` оператор за пределы блока управления, содержащего `End If` оператор.  
  
## <a name="see-also"></a>См. также раздел

- [Оператор If…Then…Else](../statements/if-then-else-statement.md)
