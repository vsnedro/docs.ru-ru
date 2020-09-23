---
title: Не удалось получить полное имя операционной системы из-за внутренней ошибки
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 744d549b9313727af2feb82e45c24b729cae7262
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91079091"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>Не удалось получить полное имя операционной системы из-за внутренней ошибки

Не удалось получить полное имя операционной системы из-за внутренней ошибки. Это может быть вызвано отсутствием WMI на текущем компьютере.  
  
 Не удалось выполнить вызов свойства `My.Computer.Info.OSFullName` . Возможная причина этой ошибки может заключаться в том, что на текущем компьютере не установлен инструментарий управления Windows (WMI).  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
1. Добавьте блок `Try...Catch` вокруг вызова свойства `My.Computer.Info.OSFullName` .  
  
2. Дополнительные сведения об инструментарии WMI и способах его установки см. в статье "инструментарий управления Windows (WMI) Core".  
  
## <a name="see-also"></a>См. также

- [My. Computer. info. OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [Обработка и создание исключений в .NET](../../standard/exceptions/index.md)
- [Попробуйте... Перехватить... Оператор finally](../language-reference/statements/try-catch-finally-statement.md)
