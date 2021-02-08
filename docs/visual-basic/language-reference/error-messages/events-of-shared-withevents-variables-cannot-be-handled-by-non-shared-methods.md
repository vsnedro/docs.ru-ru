---
description: 'Дополнительные сведения о: BC30594: события общих переменных WithEvents не могут обрабатываться методами, не являющимися общими'
title: События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: f9e8bf6e0d365c4ee747deb6be0e809904d87117
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796422"
---
# <a name="bc30594-events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>BC30594: события общих переменных WithEvents не могут обрабатываться методами, не являющимися общими

Переменная, объявленная с `Shared` модификатором, является общей переменной. Общая переменная определяет ровно одно место хранения. Переменная, объявленная с `WithEvents` модификатором, утверждает, что тип, которому принадлежит переменная, обрабатывает набор событий, которые создает переменная. Если переменной присвоено значение, то свойство, созданное `WithEvents` объявлением, отсоединяется от любого существующего обработчика событий и подключается к новому обработчику событий с помощью `Add` метода.

 **Идентификатор ошибки:** BC30594

## <a name="to-correct-this-error"></a>Исправление ошибки

- Объявите обработчик событий `Shared` .

## <a name="see-also"></a>См. также

- [Общий](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
