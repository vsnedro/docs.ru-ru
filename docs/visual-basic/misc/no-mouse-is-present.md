---
title: Не обнаружена мышь.
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: ceb850d98d29c232da304fbdfaddf5611714ef1a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91078857"
---
# <a name="no-mouse-is-present"></a>Не обнаружена мышь.

Было вызвано одно из свойств объекта `My.Computer.Mouse` , но на компьютере отсутствует установленная мышь или порт мыши.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Добавьте блок `Try...Catch` вокруг вызова свойства объекта `My.Computer.Mouse` .  
  
     Или...  
  
- Установите мышь на компьютере.  
  
## <a name="see-also"></a>См. также

- [My.Computer.Mouse](xref:Microsoft.VisualBasic.Devices.Mouse)
- [Обработка и создание исключений в .NET](../../standard/exceptions/index.md)
- [Попробуйте... Перехватить... Оператор finally](../language-reference/statements/try-catch-finally-statement.md)
