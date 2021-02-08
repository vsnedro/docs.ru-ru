---
description: 'Дополнительные сведения о: BC30029: производные классы не могут создавать события базового класса'
title: Производные классы не могут вызывать события базового класса
ms.date: 07/20/2015
f1_keywords:
- vbc30029
- bc30029
helpviewer_keywords:
- BC30029
ms.assetid: 63afa1c6-2f93-4512-a2f0-372455979771
ms.openlocfilehash: 68546f2654f7c34fcb309d5af68e237d5f1eac79
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796604"
---
# <a name="bc30029-derived-classes-cannot-raise-base-class-events"></a>BC30029: производные классы не могут создавать события базового класса

Событие может быть вызвано только из области объявления, в которой оно объявлено. Таким образом, класс не может создавать события из любого другого класса, даже из того, от которого он является производным.

 **Идентификатор ошибки:** BC30029

## <a name="to-correct-this-error"></a>Исправление ошибки

- Переместите `Event` оператор или `RaiseEvent` инструкцию так, чтобы они насовпадали с одним и тем же классом.

## <a name="see-also"></a>См. также

- [Оператор Event](../statements/event-statement.md)
- [Оператор RaiseEvent](../statements/raiseevent-statement.md)
