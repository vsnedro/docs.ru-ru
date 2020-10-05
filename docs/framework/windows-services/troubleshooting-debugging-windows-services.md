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
ms.openlocfilehash: 5846692fa0d90a62dd569253abbd81aa63b5798d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608898"
---
# <a name="troubleshooting-debugging-windows-services"></a><span data-ttu-id="5ccc9-104">Устранение неполадок: Отладка служб Windows</span><span class="sxs-lookup"><span data-stu-id="5ccc9-104">Troubleshooting: Debugging Windows Services</span></span>
<span data-ttu-id="5ccc9-105">При отладке приложения-службы Windows происходит взаимодействие между службой и диспетчером **Windows Service Manager**.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-105">When you debug a Windows service application, your service and the **Windows Service Manager** interact.</span></span> <span data-ttu-id="5ccc9-106">**Service Manager** запускает службу, вызывая метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, после чего 30 секунд ожидает возврат метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-106">The **Service Manager** starts your service by calling the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and then waits 30 seconds for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method to return.</span></span> <span data-ttu-id="5ccc9-107">Если метод не возвращается за это время, диспетчер отображает ошибку о невозможности запустить службу.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-107">If the method does not return in this time, the manager shows an error that the service cannot be started.</span></span>  
  
 <span data-ttu-id="5ccc9-108">При отладке метода <xref:System.ServiceProcess.ServiceBase.OnStart%2A>, как описано в статье [Практическое руководство. Отладка приложений-служб Windows](how-to-debug-windows-service-applications.md), необходимо помнить об этом 30-секундном периоде.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-108">When you debug the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method as described in [How to: Debug Windows Service Applications](how-to-debug-windows-service-applications.md), you must be aware of this 30-second period.</span></span> <span data-ttu-id="5ccc9-109">Если в методе <xref:System.ServiceProcess.ServiceBase.OnStart%2A> установить точку останова и не пройти ее за 30 секунд, диспетчер не запустит службу.</span><span class="sxs-lookup"><span data-stu-id="5ccc9-109">If you place a breakpoint in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method and do not step through it in 30 seconds, the manager will not start the service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccc9-110">См. также</span><span class="sxs-lookup"><span data-stu-id="5ccc9-110">See also</span></span>

- [<span data-ttu-id="5ccc9-111">Практическое руководство. Отладка приложений служб Windows</span><span class="sxs-lookup"><span data-stu-id="5ccc9-111">How to: Debug Windows Service Applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="5ccc9-112">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="5ccc9-112">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
