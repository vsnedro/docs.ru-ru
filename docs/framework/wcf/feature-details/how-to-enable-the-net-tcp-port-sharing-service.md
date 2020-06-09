---
title: Практическое руководство. Включение службы совместного использования портов Net.TCP
ms.date: 03/30/2017
helpviewer_keywords:
- port sharing [WCF]
- activation services [WCF]
ms.assetid: c9175af4-c27c-4765-bf45-b8f7528a7282
ms.openlocfilehash: 8b305b98d620636328866bce848411f395053485
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593156"
---
# <a name="how-to-enable-the-nettcp-port-sharing-service"></a><span data-ttu-id="a577a-102">Практическое руководство. Включение службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="a577a-102">How to: Enable the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="a577a-103">Windows Communication Foundation (WCF) использует службу Windows, называемую службой совместного использования портов net. TCP, чтобы упростить совместное использование портов TCP в нескольких процессах.</span><span class="sxs-lookup"><span data-stu-id="a577a-103">Windows Communication Foundation (WCF) uses a Windows service called the Net.TCP Port Sharing Service to facilitate the sharing of TCP ports across multiple processes.</span></span> <span data-ttu-id="a577a-104">Эта служба устанавливается как часть WCF, но служба не включена по умолчанию в качестве меры предосторожности, поэтому ее необходимо включить вручную перед первым использованием.</span><span class="sxs-lookup"><span data-stu-id="a577a-104">This service is installed as part of WCF, but the service is not enabled by default as a security precaution and so must be manually enabled prior to first use.</span></span> <span data-ttu-id="a577a-105">В настоящем разделе описывается настройка службы совместного использования портов Net.TCP с помощью оснастки консоли управления (MMC).</span><span class="sxs-lookup"><span data-stu-id="a577a-105">This topic describes how to configure the Net TCP Port Sharing Service using the Microsoft Management Console (MMC) snap-In.</span></span>  
  
 <span data-ttu-id="a577a-106">После включения службы совместного использования портов net. TCP и запуска ее вручную см [. раздел как настроить службу WCF для использования общего доступа к порту](how-to-configure-a-wcf-service-to-use-port-sharing.md) для получения сведений о настройке службы для использования этой службы.</span><span class="sxs-lookup"><span data-stu-id="a577a-106">After you enable the Net.TCP Port Sharing Service and start it manually, see [How to: Configure a WCF Service to Use Port Sharing](how-to-configure-a-wcf-service-to-use-port-sharing.md) for information about how to configure your service to use this service.</span></span>  
  
 <span data-ttu-id="a577a-107">Пример использования NET. TCP://совместного использования портов см. в разделе [Пример общего доступа к портам Net. TCP](../samples/net-tcp-port-sharing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="a577a-107">For a sample that uses net.tcp:// port sharing, see the [Net.TCP Port Sharing Sample](../samples/net-tcp-port-sharing-sample.md).</span></span>  
  
### <a name="to-enable-the-nettcp-port-sharing-service-using-mmc"></a><span data-ttu-id="a577a-108">Включение службы совместного использования портов Net.TCP с помощью консоли управления (MMC)</span><span class="sxs-lookup"><span data-stu-id="a577a-108">To enable the Net.TCP Port Sharing Service using MMC</span></span>  
  
1. <span data-ttu-id="a577a-109">В меню Пуск откройте консоль управления службами, открыв окно командной строки и введя `services.msc` или выполнив команду Run и введя `services.msc` в поле Открыть.</span><span class="sxs-lookup"><span data-stu-id="a577a-109">From the Start menu, open the Services Management Console either by opening a Command Prompt window and typing `services.msc` or by opening Run and typing `services.msc` into the Open box.</span></span>  
  
2. <span data-ttu-id="a577a-110">В столбце **имя** списка служб щелкните правой кнопкой мыши **службу общего доступа к портам Net. TCP**и выберите в меню пункт **Свойства** .</span><span class="sxs-lookup"><span data-stu-id="a577a-110">In the **Name** column of the list of services, right-click the **Net.Tcp Port Sharing Service**, and select **Properties** from the menu.</span></span>  
  
3. <span data-ttu-id="a577a-111">Чтобы включить Запуск службы вручную, в окне **Свойства** перейдите на вкладку **Общие** и в поле **Тип запуска** выберите вручную и нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="a577a-111">To enable the manual start-up of the service, in the **Properties** window select the **General** tab, and in the **Startup type** box select Manual, and then click **Apply**.</span></span>  
  
4. <span data-ttu-id="a577a-112">Чтобы запустить службу, в области состояние службы нажмите кнопку **запустить** .</span><span class="sxs-lookup"><span data-stu-id="a577a-112">To start the service,  in the Service status area, click the **Start** button.</span></span> <span data-ttu-id="a577a-113">Состояние службы теперь будет показано как "Работает".</span><span class="sxs-lookup"><span data-stu-id="a577a-113">The service status should now display "Started".</span></span>  
  
5. <span data-ttu-id="a577a-114">Чтобы вернуться к списку служб, нажмите кнопку **ОК**и закройте консоль MMC.</span><span class="sxs-lookup"><span data-stu-id="a577a-114">To return to the list of services, click the **OK**, and exit the MMC Console.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a577a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="a577a-115">Example</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a577a-116">См. также</span><span class="sxs-lookup"><span data-stu-id="a577a-116">See also</span></span>

- [<span data-ttu-id="a577a-117">Совместное использование портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="a577a-117">Net.TCP Port Sharing</span></span>](net-tcp-port-sharing.md)
- [<span data-ttu-id="a577a-118">Настройка службы совместного использования портов Net.TCP</span><span class="sxs-lookup"><span data-stu-id="a577a-118">Configuring the Net.TCP Port Sharing Service</span></span>](configuring-the-net-tcp-port-sharing-service.md)
