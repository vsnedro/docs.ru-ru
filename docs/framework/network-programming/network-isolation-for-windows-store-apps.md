---
title: Сетевая изоляция для приложений Магазина Windows
ms.date: 03/30/2017
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
ms.openlocfilehash: 0f9288b53b969838cac64c24d3c9861a0f841aca
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558463"
---
# <a name="network-isolation-for-windows-store-apps"></a><span data-ttu-id="271dc-102">Сетевая изоляция для приложений Магазина Windows</span><span class="sxs-lookup"><span data-stu-id="271dc-102">Network Isolation for Windows Store Apps</span></span>

<span data-ttu-id="271dc-103">Классы в пространствах имен <xref:System.Net>, <xref:System.Net.Http> и <xref:System.Net.Http.Headers> можно использовать для разработки классических приложений или приложений для Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="271dc-103">Classes in the <xref:System.Net>, <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces can be used to develop Windows Store  apps  or desktop apps.</span></span> <span data-ttu-id="271dc-104">При использовании в приложениях для Магазина Windows к классам из этих пространств имен применяется сетевая изоляция, которая является одной из составляющих модели обеспечения безопасности приложений в Windows 8.</span><span class="sxs-lookup"><span data-stu-id="271dc-104">When used in a Windows Store app, classes in these namespaces are affected by network isolation, part of the application security model used by Windows 8.</span></span> <span data-ttu-id="271dc-105">Чтобы обеспечить доступ к сети, в манифесте приложения для Магазина Windows необходимо включить соответствующие сетевые возможности.</span><span class="sxs-lookup"><span data-stu-id="271dc-105">The appropriate network capabilities must be enabled in the app manifest for a Windows Store app for the system to allow network access.</span></span>  
  
## <a name="checklist-for-network-isolation"></a><span data-ttu-id="271dc-106">Контрольный список для настройки сетевой изоляции</span><span class="sxs-lookup"><span data-stu-id="271dc-106">Checklist for Network Isolation</span></span>  

<span data-ttu-id="271dc-107">С помощью этого контрольного списка вы можете проверить правильность настройки сетевой изоляции в приложении для Магазина Windows.</span><span class="sxs-lookup"><span data-stu-id="271dc-107">Use this checklist to be sure that network isolation is configured for your Windows Store app.</span></span>  
  
1. <span data-ttu-id="271dc-108">Определите направление запросов на доступ к сети, используемых приложением.</span><span class="sxs-lookup"><span data-stu-id="271dc-108">Determine the direction of network access requests needed by the app.</span></span> <span data-ttu-id="271dc-109">Это могут быть либо исходящие от клиента запросы, либо входящие незапрошенные запросы, либо сочетание сетевых запросов обоих видов.</span><span class="sxs-lookup"><span data-stu-id="271dc-109">This can be either outbound client-initiated requests or inbound unsolicited requests or it could be a combination of both of these network request types.</span></span>  
  
2. <span data-ttu-id="271dc-110">Определите тип сетевых ресурсов, с которыми будет взаимодействовать приложение.</span><span class="sxs-lookup"><span data-stu-id="271dc-110">Determine the type of network resources that the app will communicate with.</span></span> <span data-ttu-id="271dc-111">Приложение может взаимодействовать с доверенными ресурсами в домашней или рабочей сети.</span><span class="sxs-lookup"><span data-stu-id="271dc-111">An app may need to communicate with trusted resources on a Home or Work network.</span></span> <span data-ttu-id="271dc-112">Приложение может взаимодействовать с ресурсами в Интернете.</span><span class="sxs-lookup"><span data-stu-id="271dc-112">An app might need to communicate with resources on the Internet.</span></span> <span data-ttu-id="271dc-113">Приложению может требоваться доступ к обоим типам сетевых ресурсов.</span><span class="sxs-lookup"><span data-stu-id="271dc-113">An app might need access to both types of network resources.</span></span>  
  
3. <span data-ttu-id="271dc-114">Настройте минимально необходимые возможности сетевой изоляции в манифесте приложения.</span><span class="sxs-lookup"><span data-stu-id="271dc-114">Configure the minimum-required networking isolation capabilities in the app manifest.</span></span>  
  
4. <span data-ttu-id="271dc-115">Разверните и запустите приложение, чтобы проверить его с использованием средств сетевой изоляции, предусмотренных для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="271dc-115">Deploy and run your app to test it using the network isolation tools provided for troubleshooting.</span></span>  
  
<span data-ttu-id="271dc-116">Дополнительные сведения о средствах настройки сетевых возможностей и изоляции, которые используются для устранения неполадок с сетевой изоляцией, см. в статье [Практическое руководство. Настройка возможностей сетевой изоляции](/previous-versions/windows/apps/hh770532(v=win.10)) в документации разработчика для Магазина Windows 8.x.</span><span class="sxs-lookup"><span data-stu-id="271dc-116">For more detailed information on how to configure network capabilities and isolation tools used for troubleshooting network isolation, see [How to configure network isolation capabilities](/previous-versions/windows/apps/hh770532(v=win.10)) in the Windows 8.x Store developer documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="271dc-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="271dc-117">See also</span></span>

- <span data-ttu-id="271dc-118">[Соединение с веб-службой](/previous-versions/windows/apps/hh761504(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="271dc-118">[Connecting to a web service](/previous-versions/windows/apps/hh761504(v=win.10))</span></span>
- <span data-ttu-id="271dc-119">[Рекомендации и контрольный список для настройки сетевой изоляции](/previous-versions/windows/apps/hh770532(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="271dc-119">[Guidelines and checklist for network isolation](/previous-versions/windows/apps/hh770532(v=win.10))</span></span>
- <span data-ttu-id="271dc-120">[Краткое руководство. Подключение с помощью HttpClient](/previous-versions/windows/apps/hh781239(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="271dc-120">[Quickstart: Connecting using HttpClient](/previous-versions/windows/apps/hh781239(v=win.10))</span></span>
- <span data-ttu-id="271dc-121">[Как использовать обработчики HttpClient](/previous-versions/windows/apps/hh781241(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="271dc-121">[How to use HttpClient handlers](/previous-versions/windows/apps/hh781241(v=win.10))</span></span>
- <span data-ttu-id="271dc-122">[Как защитить подключения HttpClient](/previous-versions/windows/apps/hh781240(v=win.10))</span><span class="sxs-lookup"><span data-stu-id="271dc-122">[How to secure HttpClient connections](/previous-versions/windows/apps/hh781240(v=win.10))</span></span>
- [<span data-ttu-id="271dc-123">Пример HttpClient</span><span class="sxs-lookup"><span data-stu-id="271dc-123">HttpClient Sample</span></span>](https://code.msdn.microsoft.com/windowsapps/HttpClient-sample-55700664)
