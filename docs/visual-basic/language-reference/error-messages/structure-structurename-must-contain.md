---
title: Структура <structurename> должна содержать по крайней мере один экземпляр переменной члена или экземпляр объявления события, не помеченный как Custom
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: a350940cf052aa8fbee4a1e3c61cbeaa4e37408a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870578"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>Структура \<structurename> должна содержать по крайней мере один экземпляр переменной члена или экземпляр объявления события, не помеченный как Custom

Определение структуры не содержит никаких общих переменных или необщих нестандартных событий.  
  
 Каждая структура должна иметь либо переменную, либо событие, которое применяется к каждому конкретному экземпляру (несовместное использование), а не ко всем экземплярам совместно ([Общий](../modifiers/shared.md)). Необщие константы, свойства и процедуры не соответствуют этому требованию. Кроме того, если нет необщих переменных и только одно несовместное событие, это событие не может быть `Custom` событием.  
  
 **Идентификатор ошибки:** BC30941  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Определите по крайней мере одну переменную или событие, которое не является `Shared` . Если определено только одно событие, оно должно быть нестандартным, а также не общим.  
  
## <a name="see-also"></a>См. также

- [Структуры](../../programming-guide/language-features/data-types/structures.md)
- [Практическое руководство. Объявление структуры](../../programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Оператор Structure](../statements/structure-statement.md)
