---
title: Практическое руководство. Размещение службы WCF в IIS
description: Узнайте, как создать службу WCF, размещенную в службы IIS (IIS). Размещение в службах IIS возможно только при использовании транспорта HTTP.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b044b1c9-c1e5-4c9f-84d8-0f02f4537f8b
ms.openlocfilehash: 63549b85f7bcdd4f246005401694db8827248038
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246913"
---
# <a name="how-to-host-a-wcf-service-in-iis"></a><span data-ttu-id="2ddce-104">Практическое руководство. Размещение службы WCF в IIS</span><span class="sxs-lookup"><span data-stu-id="2ddce-104">How to: Host a WCF Service in IIS</span></span>
<span data-ttu-id="2ddce-105">В этом разделе описаны основные шаги, необходимые для создания службы Windows Communication Foundation (WCF), размещенной в службы IIS (IIS).</span><span class="sxs-lookup"><span data-stu-id="2ddce-105">This topic outlines the basic steps required to create a Windows Communication Foundation (WCF) service that is hosted in Internet Information Services (IIS).</span></span> <span data-ttu-id="2ddce-106">Предполагается, что читатель знаком со службами IIS и может использовать средство управления IIS для создания приложений служб IIS и управления такими приложениями.</span><span class="sxs-lookup"><span data-stu-id="2ddce-106">This topic assumes you are familiar with IIS and understand how to use the IIS management tool to create and manage IIS applications.</span></span> <span data-ttu-id="2ddce-107">Дополнительные сведения о службах IIS см. в разделе [службы IIS](https://www.iis.net/).</span><span class="sxs-lookup"><span data-stu-id="2ddce-107">For more information about IIS see [Internet Information Services](https://www.iis.net/).</span></span> <span data-ttu-id="2ddce-108">Служба WCF, работающая в среде IIS, обладает всеми преимуществами функций IIS, таких как перезапуск процессов, выключение в режиме простоя, мониторинг работоспособности процессов и активация на основе сообщений.</span><span class="sxs-lookup"><span data-stu-id="2ddce-108">A WCF service that runs in the IIS environment takes full advantage of IIS features, such as process recycling, idle shutdown, process health monitoring, and message-based activation.</span></span> <span data-ttu-id="2ddce-109">Для реализации этого варианта размещения требуется правильно настроить службу IIS, но не требуется включать в приложение код размещения.</span><span class="sxs-lookup"><span data-stu-id="2ddce-109">This hosting option requires that IIS be properly configured, but it does not require that any hosting code be written as part of the application.</span></span> <span data-ttu-id="2ddce-110">Размещение в службах IIS возможно только при использовании транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="2ddce-110">You can use IIS hosting only with an HTTP transport.</span></span>  
  
 <span data-ttu-id="2ddce-111">Дополнительные сведения о взаимодействии WCF и ASP.NET см. в разделе [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="2ddce-111">For more information about how WCF and ASP.NET interact, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span> <span data-ttu-id="2ddce-112">Дополнительные сведения о настройке безопасности см. в разделе [Безопасность](security.md).</span><span class="sxs-lookup"><span data-stu-id="2ddce-112">For more information about configuring security, see [Security](security.md).</span></span>  
  
 <span data-ttu-id="2ddce-113">Исходный экземпляр этого примера см. в разделе [размещение IIS с помощью встроенного кода](../samples/iis-hosting-using-inline-code.md).</span><span class="sxs-lookup"><span data-stu-id="2ddce-113">For the source copy of this example, see [IIS Hosting Using Inline Code](../samples/iis-hosting-using-inline-code.md).</span></span>  
  
### <a name="to-create-a-service-hosted-by-iis"></a><span data-ttu-id="2ddce-114">Создание службы, размещенной в IIS</span><span class="sxs-lookup"><span data-stu-id="2ddce-114">To create a service hosted by IIS</span></span>  
  
1. <span data-ttu-id="2ddce-115">Убедитесь, что службы IIS установлены и выполняются на компьютере.</span><span class="sxs-lookup"><span data-stu-id="2ddce-115">Confirm that IIS is installed and running on your computer.</span></span> <span data-ttu-id="2ddce-116">Дополнительные сведения об установке и настройке IIS см. в разделе [Установка и Настройка служб iis 7,0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista) .</span><span class="sxs-lookup"><span data-stu-id="2ddce-116">For more information about installing and configuring IIS see [Installing and Configuring IIS 7.0](https://docs.microsoft.com/iis/install/installing-iis-7/installing-necessary-iis-components-on-windows-vista)</span></span>  
  
2. <span data-ttu-id="2ddce-117">Создайте новую папку для файлов приложения с именем "Иишостедкалксервице", убедитесь, что ASP.NET имеет доступ к содержимому папки, и используйте средство управления IIS для создания нового приложения IIS, физически расположенного в этом каталоге приложения.</span><span class="sxs-lookup"><span data-stu-id="2ddce-117">Create a new folder for your application files called "IISHostedCalcService", ensure that ASP.NET has access to the contents of the folder, and use the IIS management tool to create a new IIS application that is physically located in this application directory.</span></span> <span data-ttu-id="2ddce-118">Создайте для каталога приложения псевдоним «IISHostedCalc».</span><span class="sxs-lookup"><span data-stu-id="2ddce-118">When creating an alias for the application directory use "IISHostedCalc".</span></span>  
  
3. <span data-ttu-id="2ddce-119">Создайте в каталоге приложения новый файл с именем «service.svc».</span><span class="sxs-lookup"><span data-stu-id="2ddce-119">Create a new file named "service.svc" in the application directory.</span></span> <span data-ttu-id="2ddce-120">Измените этот файл, добавив следующий @ServiceHost элемент.</span><span class="sxs-lookup"><span data-stu-id="2ddce-120">Edit this file by adding the following @ServiceHost element.</span></span>  
  
   ```
   <%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService"%>
   ```  
  
4. <span data-ttu-id="2ddce-121">В каталоге приложения создайте подкаталог App_Code.</span><span class="sxs-lookup"><span data-stu-id="2ddce-121">Create an App_Code subdirectory within the application directory.</span></span>  
  
5. <span data-ttu-id="2ddce-122">Создайте файл кода с именем Service.cs во вложенном каталоге App_Code.</span><span class="sxs-lookup"><span data-stu-id="2ddce-122">Create a code file named Service.cs in the App_Code subdirectory.</span></span>  
  
6. <span data-ttu-id="2ddce-123">Добавьте следующие операторы using в начало файла Service.cs.</span><span class="sxs-lookup"><span data-stu-id="2ddce-123">Add the following using statements to the top of the Service.cs file.</span></span>  
  
    ```csharp  
    using System;  
    using System.ServiceModel;  
    ```  
  
7. <span data-ttu-id="2ddce-124">Добавьте следующее объявление пространства имен после операторов using.</span><span class="sxs-lookup"><span data-stu-id="2ddce-124">Add the following namespace declaration after the using statements.</span></span>  
  
    ```csharp  
    namespace Microsoft.ServiceModel.Samples  
    {  
    }  
    ```  
  
8. <span data-ttu-id="2ddce-125">Определите контракт службы в пределах объявления пространства имен, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="2ddce-125">Define the service contract inside the namespace declaration as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#11)]
     [!code-vb[c_HowTo_HostInIIS#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#11)]  
  
9. <span data-ttu-id="2ddce-126">Реализуйте контракт службы после определения контракта службы, как показано в следующем коде.</span><span class="sxs-lookup"><span data-stu-id="2ddce-126">Implement the service contract after the service contract definition as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowTo_HostInIIS#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#12)]
     [!code-vb[c_HowTo_HostInIIS#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#12)]  
  
10. <span data-ttu-id="2ddce-127">Создайте в каталоге приложения файл с именем Web.config и добавьте в него следующий код конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2ddce-127">Create a file named "Web.config" in the application directory and add the following configuration code into the file.</span></span> <span data-ttu-id="2ddce-128">Во время выполнения инфраструктура WCF использует эти сведения для создания конечной точки, с которой клиентские приложения могут обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="2ddce-128">At runtime, the WCF infrastructure uses the information to construct an endpoint that client applications can communicate with.</span></span>  
  
     [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]
  
     <span data-ttu-id="2ddce-129">В этом примере конечные точки явно задаются в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2ddce-129">This example explicitly specifies endpoints in the configuration file.</span></span> <span data-ttu-id="2ddce-130">Если в службу не добавлена ни одна конечная точка, то среда выполнения добавляет конечные точки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2ddce-130">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="2ddce-131">Дополнительные сведения о конечных точках по умолчанию, привязках и поведении см. в разделе [упрощенная конфигурация](../simplified-configuration.md) и [упрощенная конфигурация для служб WCF](../samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="2ddce-131">For more information about default endpoints, bindings, and behaviors see [Simplified Configuration](../simplified-configuration.md) and [Simplified Configuration for WCF Services](../samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
11. <span data-ttu-id="2ddce-132">Чтобы проверить правильность размещения службы, откройте экземпляр окна Internet Explorer и перейдите по URL-адресу службы: `http://localhost/IISHostedCalc/Service.svc`.</span><span class="sxs-lookup"><span data-stu-id="2ddce-132">To make sure the service is hosted correctly, open an instance of Internet Explorer and browse to the service's URL: `http://localhost/IISHostedCalc/Service.svc`</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ddce-133">Пример</span><span class="sxs-lookup"><span data-stu-id="2ddce-133">Example</span></span>  
 <span data-ttu-id="2ddce-134">Далее представлен полный код службы калькулятора, размещаемой в IIS.</span><span class="sxs-lookup"><span data-stu-id="2ddce-134">The following is a complete listing of the code for the IIS hosted calculator service.</span></span>  
  
 [!code-csharp[C_HowTo_HostInIIS#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/cs/source.cs#1)]
 [!code-vb[C_HowTo_HostInIIS#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_hostiniis/vb/source.vb#1)]
 [!code-xml[c_HowTo_HostInIIS#100](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostiniis/common/web.config#100)]  
  
## <a name="see-also"></a><span data-ttu-id="2ddce-135">См. также</span><span class="sxs-lookup"><span data-stu-id="2ddce-135">See also</span></span>

- [<span data-ttu-id="2ddce-136">Размещение в службах IIS</span><span class="sxs-lookup"><span data-stu-id="2ddce-136">Hosting in Internet Information Services</span></span>](hosting-in-internet-information-services.md)
- [<span data-ttu-id="2ddce-137">Размещение служб</span><span class="sxs-lookup"><span data-stu-id="2ddce-137">Hosting Services</span></span>](../hosting-services.md)
- [<span data-ttu-id="2ddce-138">Службы WCF и ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2ddce-138">WCF Services and ASP.NET</span></span>](wcf-services-and-aspnet.md)
- [<span data-ttu-id="2ddce-139">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2ddce-139">Security</span></span>](security.md)
- <span data-ttu-id="2ddce-140">[Функции размещения Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="2ddce-140">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
