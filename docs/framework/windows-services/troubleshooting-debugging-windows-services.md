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
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="6804d-104">Устранение неполадок: Отладка служб Windows</span><span class="sxs-lookup"><span data-stu-id="6804d-104">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="6804d-105">При отладке приложения-службы Windows происходит взаимодействие между службой и диспетчером **Windows Service Manager**.</span><span class="sxs-lookup"><span data-stu-id="6804d-105">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="6804d-106">**Service Manager** запускает службу, вызывая метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, после чего 30 секунд ожидает возврат метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="6804d-106">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="6804d-107">Если метод не возвращается за это время, диспетчер отображает ошибку о невозможности запустить службу.</span><span class="sxs-lookup"><span data-stu-id="6804d-107">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="6804d-108">При отладке метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, как описано в статье [Практическое руководство. Отладка приложений-служб Windows](how-to-debug-windows-service-applications.md), необходимо помнить об этом 30-секундном периоде.</span><span class="sxs-lookup"><span data-stu-id="6804d-108">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="6804d-109">Если в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> установить точку останова и не пройти ее за 30 секунд, диспетчер не запустит службу.</span><span class="sxs-lookup"><span data-stu-id="6804d-109">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6804d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6804d-110">See also</span></span>

- [<span data-ttu-id="6804d-111">Практическое руководство. Отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="6804d-111">How to: Debug Windows Service Applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="6804d-112">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="6804d-112">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
