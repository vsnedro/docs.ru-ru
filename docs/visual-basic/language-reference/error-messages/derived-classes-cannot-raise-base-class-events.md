---
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 7b86420466d77a6aa45b1201a9375b4433e4b5ec
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92163445"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a>BC30029: производные классы не могут создавать события базового класса

Событие может быть вызвано только из области объявления, в которой оно объявлено. Таким образом, класс не может создавать события из любого другого класса, даже из того, от которого он является производным.

 **Идентификатор ошибки:** BC30029

## <a name="to-correct-this-error"></a>Исправление ошибки

- Переместите `Event` оператор или `RaiseEvent` инструкцию так, чтобы они насовпадали с одним и тем же классом.

## <a name="see-also"></a>См. также

- [Оператор Event](../statements/event-statement.md)
- [Оператор RaiseEvent](../statements/raiseevent-statement.md)
