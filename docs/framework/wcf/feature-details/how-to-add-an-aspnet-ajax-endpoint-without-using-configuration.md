---
title: Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации
ms.date: 03/30/2017
ms.assetid: b05c1742-8d0a-4673-9d71-725b18a3008e
ms.openlocfilehash: 9aab53d6457aa7848fd4acea6317a30da352cc98
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579635"
---
# <a name="how-to-add-an-aspnet-ajax-endpoint-without-using-configuration"></a><span data-ttu-id="c08c2-102">Практическое руководство. Добавление конечной точки ASP.NET AJAX без использования конфигурации</span><span class="sxs-lookup"><span data-stu-id="c08c2-102">How to: Add an ASP.NET AJAX Endpoint Without Using Configuration</span></span>
<span data-ttu-id="c08c2-103">Windows Communication Foundation (WCF) позволяет создать службу, предоставляющую конечную точку с поддержкой AJAX ASP.NET, которая может быть вызвана из JavaScript на веб-сайте клиента.</span><span class="sxs-lookup"><span data-stu-id="c08c2-103">Windows Communication Foundation (WCF) allows you to create a service that exposes an ASP.NET AJAX-enabled endpoint that can be called from JavaScript on a client Web site.</span></span> <span data-ttu-id="c08c2-104">Для создания этой конечной точки можно воспользоваться либо файлом конфигурации (как и для всех остальных конечных точек WCF), либо методом, не требующим никаких элементов конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c08c2-104">To create such an endpoint, you can either use a configuration file, as with all other WCF endpoints, or use a method that does not require any configuration elements.</span></span> <span data-ttu-id="c08c2-105">В этом разделе показано решение этой задачи вторым методом.</span><span class="sxs-lookup"><span data-stu-id="c08c2-105">This topic demonstrates the second approach.</span></span>  
  
 <span data-ttu-id="c08c2-106">Создание служб с конечными точками ASP.NET AJAX без конфигурации возможно только при размещении служб в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="c08c2-106">To create services with ASP.NET AJAX endpoints without configuration, the services must be hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="c08c2-107">Чтобы активировать конечную точку ASP.NET AJAX с помощью этого подхода, укажите в <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> качестве параметра фабрики в директиве [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) в SVC – файле.</span><span class="sxs-lookup"><span data-stu-id="c08c2-107">To activate an ASP.NET AJAX endpoint using this approach, specify the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> as the Factory parameter in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive in the .svc file.</span></span> <span data-ttu-id="c08c2-108">Эта пользовательская фабрика является компонентом, который автоматически настраивает конечную точку ASP.NET AJAX так, чтобы ее можно было вызвать из кода JavaScript на веб-сайте клиента.</span><span class="sxs-lookup"><span data-stu-id="c08c2-108">This custom factory is the component that automatically configures an ASP.NET AJAX endpoint so that it can be called from JavaScript on a client Web site.</span></span>  
  
 <span data-ttu-id="c08c2-109">Рабочий пример см. в разделе [Служба AJAX без настройки](../samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c08c2-109">For a working example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
 <span data-ttu-id="c08c2-110">Сведения о настройке конечной точки ASP.NET AJAX с помощью элементов конфигурации см. в разделе [как использовать конфигурацию для добавления конечной точки ASP.NET AJAX](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="c08c2-110">For an outline of how to configure an ASP.NET AJAX endpoint using configuration elements, see [How to: Use Configuration to Add an ASP.NET AJAX Endpoint](how-to-use-configuration-to-add-an-aspnet-ajax-endpoint.md).</span></span>  
  
### <a name="to-create-a-basic-wcf-service"></a><span data-ttu-id="c08c2-111">Создание базовой службы WCF</span><span class="sxs-lookup"><span data-stu-id="c08c2-111">To create a basic WCF service</span></span>  
  
1. <span data-ttu-id="c08c2-112">Определите базовый контракт службы WCF с интерфейсом, помеченным <xref:System.ServiceModel.ServiceContractAttribute> атрибутом.</span><span class="sxs-lookup"><span data-stu-id="c08c2-112">Define a basic WCF service contract with an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="c08c2-113">Пометьте каждую операцию атрибутом <xref:System.ServiceModel.OperationContractAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c08c2-113">Mark each operation with the <xref:System.ServiceModel.OperationContractAttribute>.</span></span> <span data-ttu-id="c08c2-114">Не забудьте задать свойство <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A>.</span><span class="sxs-lookup"><span data-stu-id="c08c2-114">Be sure to set the <xref:System.ServiceModel.ServiceContractAttribute.Namespace%2A> property.</span></span>  
  
    ```csharp  
    [ServiceContract(Namespace = "MyService")]]  
    public interface ICalculator  
    {  
        [OperationContract]  
        // This operation returns the sum of d1 and d2.  
        double Add(double n1, double n2);  
  
        //Other operations omitted…  
  
    }  
    ```  
  
2. <span data-ttu-id="c08c2-115">Реализуйте контракт службы `ICalculator` с помощью класса `CalculatorService`.</span><span class="sxs-lookup"><span data-stu-id="c08c2-115">Implement the `ICalculator` service contract with a `CalculatorService`.</span></span>  
  
    ```csharp  
    public class CalculatorService : ICalculator  
    {  
        public double Add(double n1, double n2)  
        {  
            return n1 + n2;  
        }  
  
    //Other operations omitted…  
    ```  
  
3. <span data-ttu-id="c08c2-116">Определите пространство имен для реализаций `ICalculator` и `CalculatorService`, заключив их в блок пространства имен.</span><span class="sxs-lookup"><span data-stu-id="c08c2-116">Define a namespace for the `ICalculator` and `CalculatorService` implementations by wrapping them in a namespace block.</span></span>  
  
    ```csharp  
    Namespace Microsoft.Ajax.Samples  
    {  
        //Include the code for ICalculator and Caculator here.  
    }  
    ```  
  
### <a name="to-host-the-service-in-internet-information-services-without-configuration"></a><span data-ttu-id="c08c2-117">Размещение службы в службах IIS без конфигурации</span><span class="sxs-lookup"><span data-stu-id="c08c2-117">To host the service in Internet Information Services without configuration</span></span>  
  
1. <span data-ttu-id="c08c2-118">Создайте в приложении новый файл с именем "service" и расширением .svc.</span><span class="sxs-lookup"><span data-stu-id="c08c2-118">Create a new file named service with a .svc extension in the application.</span></span> <span data-ttu-id="c08c2-119">Измените этот файл, добавив соответствующие сведения об директиве [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) для службы.</span><span class="sxs-lookup"><span data-stu-id="c08c2-119">Edit this file by adding the appropriate [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive information for the service.</span></span> <span data-ttu-id="c08c2-120">Укажите, что <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> класс должен использоваться в директиве [ \@ ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) для автоматической настройки конечной точки ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="c08c2-120">Specify that the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is to be used in the [\@ServiceHost](../../configure-apps/file-schema/wcf-directive/servicehost.md) directive to automatically configure an ASP.NET AJAX endpoint.</span></span>  
  
    ```text
    <%@ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Ajax.Samples.CalculatorService"  
        Factory=System.ServiceModel.Activation.WebScriptServiceHostFactory  
    %>  
    ```  
  
2. <span data-ttu-id="c08c2-121">Создайте службу и вызовите ее из клиента.</span><span class="sxs-lookup"><span data-stu-id="c08c2-121">Build the service and call it from the client.</span></span> <span data-ttu-id="c08c2-122">Internet Information Services (IIS) активирует данную службу при вызове.</span><span class="sxs-lookup"><span data-stu-id="c08c2-122">Internet Information Services (IIS) activates the service when called.</span></span> <span data-ttu-id="c08c2-123">Дополнительные сведения о размещении в службах IIS см. в разделе [как разместить службу WCF в IIS](how-to-host-a-wcf-service-in-iis.md).</span><span class="sxs-lookup"><span data-stu-id="c08c2-123">For more information about hosting in IIS, see [How to: Host a WCF Service in IIS](how-to-host-a-wcf-service-in-iis.md).</span></span>  
  
### <a name="to-call-the-service"></a><span data-ttu-id="c08c2-124">Вызов службы</span><span class="sxs-lookup"><span data-stu-id="c08c2-124">To call the service</span></span>  
  
1. <span data-ttu-id="c08c2-125">Конечная точка настраивается по пустому адресу относительно SVC-файла, поэтому служба доступна и может быть вызвана путем отправки запросов к службе. svc/-например \<operation> , Service. svc/Add для `Add` операции.</span><span class="sxs-lookup"><span data-stu-id="c08c2-125">The endpoint is configured at an empty address relative to the .svc file, so the service is now available and can be invoked by sending requests to service.svc/\<operation> - for example, service.svc/Add for the `Add` operation.</span></span> <span data-ttu-id="c08c2-126">Для этого нужно указать URL-адрес службы в коллекции "Скрипты" в средстве управления диспетчера скриптов ASP.NET AJAX.</span><span class="sxs-lookup"><span data-stu-id="c08c2-126">You can use it by entering the service URL into the Scripts collection of the ASP.NET AJAX Script Manager control.</span></span> <span data-ttu-id="c08c2-127">Пример см. в разделе [Служба AJAX без настройки](../samples/ajax-service-without-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="c08c2-127">For an example, see the [AJAX Service Without Configuration](../samples/ajax-service-without-configuration.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c08c2-128">Пример</span><span class="sxs-lookup"><span data-stu-id="c08c2-128">Example</span></span>  
  
 <span data-ttu-id="c08c2-129">Автоматически настраиваемая конечная точка создается по пустому адресу, заданному относительно базового URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="c08c2-129">The automatically-configured endpoint is created at an empty address relative to the base URL.</span></span> <span data-ttu-id="c08c2-130">Этот метод также допускает добавление и использование файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c08c2-130">A configuration file can also be added and used with this approach.</span></span> <span data-ttu-id="c08c2-131">Если в файле конфигурации содержатся определения конечных точек, эти конечные точки добавляются к автоматически настраиваемой конечной точке.</span><span class="sxs-lookup"><span data-stu-id="c08c2-131">If the configuration file contains endpoint definitions, these endpoints are added to the automatically-configured endpoint.</span></span>  
  
 <span data-ttu-id="c08c2-132">Например, service.svc использует фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, а в каталоге службы содержится файл Web.config, который определяет конечную точку для той же службы с помощью привязки <xref:System.ServiceModel.BasicHttpBinding> по относительному адресу "soap".</span><span class="sxs-lookup"><span data-stu-id="c08c2-132">For example, service.svc uses the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> and the service directory contains a Web.config file that defines an endpoint for the same service using the <xref:System.ServiceModel.BasicHttpBinding> at the "soap" relative address.</span></span> <span data-ttu-id="c08c2-133">В этом случае служба содержит две конечные точки: одну - в файле service.svc (отвечающую на запросы ASP.NET AJAX), другую - в service.svc/soap (отвечающую на запросы SOAP).</span><span class="sxs-lookup"><span data-stu-id="c08c2-133">In this case, the service contains two endpoints: one at service.svc (which responds to ASP.NET AJAX requests) and another at service.svc/soap (which responds to SOAP requests).</span></span>  
  
 <span data-ttu-id="c08c2-134">Если файл конфигурации определяет конечную точку по пустому относительному адресу и используется фабрика узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>, создается исключение, происходит сбой запуска службы.</span><span class="sxs-lookup"><span data-stu-id="c08c2-134">If the configuration file defines an endpoint at an empty relative address and the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> is used, an exception is thrown and the service fails to start.</span></span>  
  
 <span data-ttu-id="c08c2-135">С помощью конфигурации невозможно изменить параметры автоматически настраиваемой конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c08c2-135">You cannot use configuration to modify settings on the automatically-configured endpoint.</span></span> <span data-ttu-id="c08c2-136">При необходимости изменить какой-либо параметр (например, квоту средств чтения) не следует использовать метод без конфигурации, т. е. удалять фабрику узла <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> из файла .svc и создавать запись конфигурации для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="c08c2-136">If any setting (such as a reader quota) must be modified, you must not use the configuration-free approach by removing the <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> from the .svc file and creating a configuration entry for the endpoint.</span></span>  
  
 <span data-ttu-id="c08c2-137">Если службе требуется режим совместимости с ASP.NET (например, если служба использует класс <xref:System.Web.HttpContext> или механизмы авторизации ASP.NET), для включения этого режима все равно понадобится файл конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c08c2-137">If your service requires ASP.NET Compatibility Mode - for example, if it uses the <xref:System.Web.HttpContext> class or ASP.NET authorization mechanisms - a configuration file is still required to turn on this mode.</span></span> <span data-ttu-id="c08c2-138">Обязательный элемент конфигурации — это [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) элемент, который должен быть добавлен следующим образом.</span><span class="sxs-lookup"><span data-stu-id="c08c2-138">The configuration element required is the [\<serviceHostingEnvironment>](../../configure-apps/file-schema/wcf/servicehostingenvironment.md) element, which must be added as follows.</span></span>  
  
 `<system.serviceModel>`  
  
 `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" /> </system.serviceModel>`  
  
 <span data-ttu-id="c08c2-139">Дополнительные сведения см. в разделе [WCF Services and ASP.NET](wcf-services-and-aspnet.md) .</span><span class="sxs-lookup"><span data-stu-id="c08c2-139">For more information, see the [WCF Services and ASP.NET](wcf-services-and-aspnet.md) topic.</span></span>  
  
 <span data-ttu-id="c08c2-140">Класс <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> наследуется от класса <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span><span class="sxs-lookup"><span data-stu-id="c08c2-140">The <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory> class is a derived class of <xref:System.ServiceModel.Activation.ServiceHostFactory>.</span></span> <span data-ttu-id="c08c2-141">Подробное описание механизма фабрики узлов служб см. в разделе [расширение размещения с помощью ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) .</span><span class="sxs-lookup"><span data-stu-id="c08c2-141">For a detailed explanation of the service host factory mechanism, see the [Extending Hosting Using ServiceHostFactory](../extending/extending-hosting-using-servicehostfactory.md) topic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c08c2-142">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="c08c2-142">See also</span></span>

- [<span data-ttu-id="c08c2-143">Создание служб WCF для ASP.NET AJAX</span><span class="sxs-lookup"><span data-stu-id="c08c2-143">Creating WCF Services for ASP.NET AJAX</span></span>](creating-wcf-services-for-aspnet-ajax.md)
- [<span data-ttu-id="c08c2-144">Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF</span><span class="sxs-lookup"><span data-stu-id="c08c2-144">How to: Migrate AJAX-Enabled ASP.NET Web Services to WCF</span></span>](how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)
