---
description: 'Дополнительные сведения о: BC32022: " <eventname> " является событием и не может вызываться напрямую'
title: <eventname> является событием, поэтому его прямой вызов невозможен
ms.date: 07/20/2015
f1_keywords:
- bc32022
- vbc32022
helpviewer_keywords:
- BC32022
ms.assetid: 4dcfcb8d-a9fa-46a7-a034-29d9ff3a59b3
ms.openlocfilehash: f9d4b8fe54e1101e7963933f871cf5af2c1af903
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796448"
---
# <a name="bc32022-eventname-is-an-event-and-cannot-be-called-directly"></a>BC32022: " \<eventname> " является событием и не может вызываться напрямую

"<`eventname`>" является событием, поэтому его нельзя вызывать напрямую. `RaiseEvent`Для вызова события используйте инструкцию.

 Вызов процедуры задает событие для имени процедуры. Обработчик событий — это процедура, но само событие является сигнальным устройством, которое должно быть вызвано и обработано.

 **Идентификатор ошибки:** BC32022

## <a name="to-correct-this-error"></a>Исправление ошибки

- Используйте `RaiseEvent` оператор, чтобы сообщить о событии и вызвать процедуру или процедуры, которые ее обработают.

## <a name="see-also"></a>См. также

- [Оператор RaiseEvent](../statements/raiseevent-statement.md)
