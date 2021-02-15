---
description: 'Дополнительные сведения о: мышь отсутствует'
title: Не обнаружена мышь.
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: 1964f1def655a1e38ce2b8919a69ab2e6ac929a7
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2021
ms.locfileid: "100479131"
---
# <a name="no-mouse-is-present"></a>Не обнаружена мышь.

Было вызвано одно из свойств объекта `My.Computer.Mouse` , но на компьютере отсутствует установленная мышь или порт мыши.  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
- Добавьте блок `Try...Catch` вокруг вызова свойства объекта `My.Computer.Mouse` .  
  
     Или...  
  
- Установите мышь на компьютере.  
  
## <a name="see-also"></a>См. также раздел

- [My.Computer.Mouse](xref:Microsoft.VisualBasic.Devices.Mouse)
- [Обработка и создание исключений в .NET](../../standard/exceptions/index.md)
- [Оператор Try...Catch...Finally](../language-reference/statements/try-catch-finally-statement.md)
