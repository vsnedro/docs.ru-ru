---
title: Контексты объявления и уровни доступа по умолчанию
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: a659481b34b8b44f1f387b464d5d9656ed98ab3f
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874952"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Контексты объявления и уровни доступа по умолчанию (Visual Basic)

В этом разделе описано, какие типы Visual Basic могут быть объявлены, в которых можно объявлять другие типы, а также уровни доступа по умолчанию, если они не указаны.  
  
## <a name="declaration-context-levels"></a>Уровни контекста объявления  

 *Контекстом объявления* программного элемента является область кода, в которой он объявлен. Часто это другой программный элемент, который затем называется *содержащим элементом*.  
  
 Ниже приведены уровни для контекстов объявления.  
  
- *Уровень пространства имен* — в исходном файле или пространстве имен, но не в классе, структуре, модуле или интерфейсе  
  
- *Уровень модуля* — в классе, структуре, модуле или интерфейсе, но не внутри процедуры или блока  
  
- *Уровень процедуры* — внутри процедуры или блока (например, `If` или `For` ).  
  
 В следующей таблице показаны уровни доступа по умолчанию для различных объявленных программных элементов в зависимости от контекстов объявления.  
  
|Объявленный элемент|Уровень пространства имен|Уровень модуля|Уровень процедуры|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([оператор Dim](dim-statement.md))|Не разрешено|`Private` ( `Public` в `Structure` , недопустимо в `Interface` )|`Public`|  
|Constant ([оператор Const](const-statement.md))|Не разрешено|`Private` ( `Public` в `Structure` , недопустимо в `Interface` )|`Public`|  
|Enumeration ([оператор Enum](enum-statement.md))|`Friend`|`Public`|Не разрешено|  
|Class ([оператор Class](class-statement.md))|`Friend`|`Public`|Не разрешено|  
|Structure ([оператор Structure](structure-statement.md))|`Friend`|`Public`|Не разрешено|  
|Module ([оператор Module](module-statement.md))|`Friend`|Нельзя использовать|Нельзя использовать|  
|Interface ([оператор Interface](interface-statement.md))|`Friend`|`Public`|Не разрешено|  
|PROCEDURE ([оператор Function](function-statement.md), [оператор подвыражения](sub-statement.md))|Нельзя использовать|`Public`|Нельзя использовать|  
|Внешняя ссылка ([Инструкция DECLARE](declare-statement.md))|Не разрешено|`Public` (не допускается в `Interface` )|Не разрешено|  
|Оператор operator (оператор[operator](operator-statement.md))|Не разрешено|`Public` (не допускается в `Interface` или `Module` )|Не разрешено|  
|Property ([Оператор Property](property-statement.md))|Нельзя использовать|`Public`|Нельзя использовать|  
|Свойство по умолчанию ([по умолчанию](../modifiers/default.md))|Не разрешено|`Public` (не допускается в `Module` )|Не разрешено|  
|Event ([оператор Event](event-statement.md))|Нельзя использовать|`Public`|Нельзя использовать|  
|Delegate ([оператор Delegate](delegate-statement.md))|`Friend`|`Public`|Не разрешено|  
  
 Дополнительные сведения см. [в разделе уровни доступа в Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>См. также

- [Friend](../modifiers/friend.md)
- [Частная](../modifiers/private.md)
- [Общедоступная](../modifiers/public.md)
