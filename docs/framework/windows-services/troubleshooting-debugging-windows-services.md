---
title: 'Устранение неполадок: Отладка служб Windows'
description: Начните работу с отладкой в служб Windows. При отладке приложения-службы Windows происходит взаимодействие между службой и Windows Service Manager.
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- troubleshooting service applications
- services, troubleshooting
- troubleshooting debugging, Windows Services
- Windows Service applications, debugging
- services, debugging
- Windows Service applications, troubleshooting
ms.assetid: cf859d4c-f04c-4cb7-81e3-bc7de8bea190
author: ghogen
ms.openlocfilehash: 935f5dcbd369ba5d723cc0e947ba708afdd590ea
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925544"
---
# <a name="troubleshooting-debugging-windows-services"></a>Устранение неполадок: Отладка служб Windows
При отладке приложения-службы Windows происходит взаимодействие между службой и диспетчером **Windows Service Manager**. **Service Manager** запускает службу, вызывая метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, после чего 30 секунд ожидает возврат метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>. Если метод не возвращается за это время, диспетчер отображает ошибку о невозможности запустить службу.  
  
 При отладке метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, как описано в статье [Практическое руководство. Отладка приложений-служб Windows](how-to-debug-windows-service-applications.md), необходимо помнить об этом 30-секундном периоде. Если в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> установить точку останова и не пройти ее за 30 секунд, диспетчер не запустит службу.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Отладка приложений служб Windows](how-to-debug-windows-service-applications.md)
- [Знакомство с приложениями служб Windows](introduction-to-windows-service-applications.md)
