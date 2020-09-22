---
title: <eventname> является событием, поэтому его прямой вызов невозможен
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 3366bc215a45cd7de9dc2de285758a78144df509
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874315"
---
# <a name="eventname-is-an-event-and-cannot-be-called-directly"></a>\<eventname> является событием, поэтому его прямой вызов невозможен

"<`eventname`>" является событием, поэтому его нельзя вызывать напрямую. `RaiseEvent`Для вызова события используйте инструкцию.  
  
 Вызов процедуры задает событие для имени процедуры. Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть вызвано и обработано.  
  
 **Идентификатор ошибки:** BC32022  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Используйте `RaiseEvent` оператор, чтобы сообщить о событии и вызвать процедуру или процедуры, которые ее обработают.  
  
## <a name="see-also"></a>См. также

- [Оператор RaiseEvent](../statements/raiseevent-statement.md)
