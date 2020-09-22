---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 0233a1584c5e871506b5c4762e98874c343f19b8
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874480"
---
# <a name="derived-classes-cannot-raise-base-class-events"></a>Производные классы не могут вызывать события базового класса

Событие может быть вызвано только из области объявления, в которой оно объявлено. Таким образом, класс не может создавать события из любого другого класса, даже из того, от которого он является производным.  
  
 **Идентификатор ошибки:** BC30029  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Переместите `Event` оператор или `RaiseEvent` инструкцию так, чтобы они насовпадали с одним и тем же классом.  
  
## <a name="see-also"></a>См. также

- [Оператор Event](../statements/event-statement.md)
- [Оператор RaiseEvent](../statements/raiseevent-statement.md)
