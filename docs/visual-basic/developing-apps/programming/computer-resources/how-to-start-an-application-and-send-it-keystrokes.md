---
description: 'Узнайте подробнее о: Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)'
title: Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)
ms.date: 10/23/2019
helpviewer_keywords:
- keystrokes, sending
- Shell command example [Visual Basic]
- processes, starting and sending keystrokes
- SendKeys.SendWait examples
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
ms.openlocfilehash: ea54b940b528e0833d9c7a6cbef67f65a4cb4f6b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99666463"
---
# <a name="how-to-start-an-application-and-send-it-keystrokes-visual-basic"></a>Практическое руководство. Запуск приложения и отправка ему нажатий клавиш (Visual Basic)

Этот пример использует метод <xref:Microsoft.VisualBasic.Interaction.Shell%2A> для запуска приложения "Блокнот", а затем распечатывает предложение, отправляя нажатия клавиш с помощью метода [My.Computer.Keyboard.SendKeys](xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A).

## <a name="example"></a>Пример

[!code-vb[VbVbalrMyComputer#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#25)]

## <a name="robust-programming"></a>Отказоустойчивость

Если приложение с запрошенным идентификатором процесса не найдено, возникает исключение <xref:System.ArgumentException>.  
  
## <a name="net-framework-security"></a>Безопасность .NET Framework

Вызов функции `Shell` требует полного доверия (класс <xref:System.Security.SecurityException>).

## <a name="see-also"></a>См. также раздел

- <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>
- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>
