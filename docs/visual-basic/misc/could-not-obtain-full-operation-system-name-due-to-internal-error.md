---
title: Не удалось получить полное имя операционной системы из-за внутренней ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 67e8fb5e906800d28bf15714463b7ff6ae585693
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402282"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Не удалось получить полное имя операционной системы из-за внутренней ошибки
Не удалось получить полное имя операционной системы из-за внутренней ошибки. Это может быть вызвано отсутствием WMI на текущем компьютере.  
  
 Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` . Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .  
  
2. Дополнительные сведения об инструментарии WMI и способах его установки см. в статье "инструментарий управления Windows (WMI) Core".  
  
## <a name="see-also"></a>См. также раздел

- [My. Computer. info. OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [Обработка и создание исключений в .NET](../../standard/exceptions/index.md)
- [Оператор Try…Catch…Finally](../language-reference/statements/try-catch-finally-statement.md)
