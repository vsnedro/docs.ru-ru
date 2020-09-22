---
title: Оператор не может завершить блок за пределами однострочной инструкции If
ms.date: 07/20/2015
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords:
- BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
ms.openlocfilehash: 5e75c29e57a9c04c66e6bca79d99bb18c513f667
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870741"
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-if-statement"></a>Оператор не может завершить блок за пределами однострочной инструкции If

Однострочный `If` оператор содержит несколько операторов, разделенных двоеточиями (:), одна из которых является `End` оператором для блока управления за пределами однострочного `If` . Однострочные `If` операторы не используют `End If` инструкцию.  
  
 **Идентификатор ошибки:** BC32005  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Переместите однострочный `If` оператор за пределы блока управления, содержащего `End If` оператор.  
  
## <a name="see-also"></a>См. также

- [Оператор If…Then…Else](../statements/if-then-else-statement.md)
