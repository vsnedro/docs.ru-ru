---
title: События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
ms.date: 07/20/2015
f1_keywords:
- bc30594
- vbc30594
helpviewer_keywords:
- BC30594
ms.assetid: 5b9fceb4-ab11-41bb-ad3b-6f1a9da8ae7e
ms.openlocfilehash: fc163c1069aa6f41766664e0fa5f5a9c34a1f73d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409573"
---
# <a name="events-of-shared-withevents-variables-cannot-be-handled-by-non-shared-methods"></a>События общих переменных WithEvents не могут обрабатываться не используемыми совместно методами
Переменная, объявленная с `Shared` модификатором, является общей переменной. Общая переменная определяет ровно одно место хранения. Переменная, объявленная с `WithEvents` модификатором, утверждает, что тип, которому принадлежит переменная, обрабатывает набор событий, которые создает переменная. Если переменной присвоено значение, то свойство, созданное `WithEvents` объявлением, отсоединяется от любого существующего обработчика событий и подключается к новому обработчику событий с помощью `Add` метода.  
  
 **Идентификатор ошибки:** BC30594  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Объявите обработчик событий `Shared` .  
  
## <a name="see-also"></a>См. также раздел

- [Общий](../modifiers/shared.md)
- [WithEvents](../modifiers/withevents.md)
