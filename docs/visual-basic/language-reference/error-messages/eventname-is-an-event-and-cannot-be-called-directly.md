---
title: <eventname> является событием, поэтому его прямой вызов невозможен
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: 246cb92daa2c838c95f695542f33cf02af42764d
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161989"
---
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a>BC32022: " \<eventname> " является событием и не может вызываться напрямую

"<`eventname`>" является событием, поэтому его нельзя вызывать напрямую. `RaiseEvent`Для вызова события используйте инструкцию.

 Вызов процедуры задает событие для имени процедуры. Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть вызвано и обработано.

 **Идентификатор ошибки:** BC32022

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте `RaiseEvent` оператор, чтобы сообщить о событии и вызвать процедуру или процедуры, которые ее обработают.

## <a name="see-also"></a>См. также

- [Оператор RaiseEvent](../statements/raiseevent-statement.md)
