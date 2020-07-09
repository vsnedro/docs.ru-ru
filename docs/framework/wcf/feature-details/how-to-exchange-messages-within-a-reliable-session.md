---
title: Практическое руководство. Обмен сообщениями в рамках надежного сеанса
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 39dd6636f80b107ced1caac29869c6c66e67e21e
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86052043"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="6c5e6-102">Практическое руководство. Обмен сообщениями в рамках надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="6c5e6-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="6c5e6-103">В этом разделе описываются действия, необходимые, чтобы разрешить надежные сеансы с помощью одной из привязок, предоставляемых системой, которая поддерживает такие сеансы, но не по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="6c5e6-104">Надежный сеанс можно включить принудительно с помощью кода или декларативно в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="6c5e6-105">В этой процедуре используются файлы конфигурации клиента и службы для включения надежного сеанса и указания того, что сообщения поступают в том же порядке, в котором они были отправлены.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="6c5e6-106">Основная часть этой процедуры состоит в том, что элемент конфигурации конечной точки содержит `bindingConfiguration` атрибут, который ссылается на конфигурацию привязки с именем `Binding1` .</span><span class="sxs-lookup"><span data-stu-id="6c5e6-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="6c5e6-107">[**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md)Элемент Configuration ссылается на это имя, чтобы включить надежные сеансы, задав `enabled` атрибуту [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) элемента значение `true` .</span><span class="sxs-lookup"><span data-stu-id="6c5e6-107">The [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) element to `true`.</span></span> <span data-ttu-id="6c5e6-108">Можно обеспечить доставку сообщений в порядке их отправки для надежного сеанса, присвоив атрибуту `ordered` значение `true`.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="6c5e6-109">Исходный экземпляр этого примера см. в разделе [WS надежный сеанс](../samples/ws-reliable-session.md).</span><span class="sxs-lookup"><span data-stu-id="6c5e6-109">For the source copy of this example, see [WS Reliable Session](../samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="6c5e6-110">Настройка службы с помощью WSHttpBinding для использования надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="6c5e6-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="6c5e6-111">Определите контракт службы для данного типа службы.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="6c5e6-112">Реализуйте контракт службы в классе службы.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="6c5e6-113">Обратите внимание, что адрес или сведения о привязке не указываются внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="6c5e6-114">Вам не нужно писать код для получения адреса или сведений о привязке из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="6c5e6-115">Создайте файл *Web.config* , чтобы настроить конечную точку для `CalculatorService` , в которой <xref:System.ServiceModel.WSHttpBinding> включена функция with надежный сеанс и упорядоченная доставка сообщений.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="6c5e6-116">Создайте файл *Service. svc* , содержащий строку:</span><span class="sxs-lookup"><span data-stu-id="6c5e6-116">Create a *Service.svc* file that contains the line:</span></span>

   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. <span data-ttu-id="6c5e6-117">Поместите файл *Service. svc* в виртуальный каталог службы IIS (IIS).</span><span class="sxs-lookup"><span data-stu-id="6c5e6-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="6c5e6-118">Настройка клиента с помощью WSHttpBinding для использования надежного сеанса</span><span class="sxs-lookup"><span data-stu-id="6c5e6-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="6c5e6-119">Используйте [служебную программу метаданных ServiceModel (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) из командной строки, чтобы создать код из метаданных службы:</span><span class="sxs-lookup"><span data-stu-id="6c5e6-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="6c5e6-120">Созданный клиент содержит `ICalculator` интерфейс, определяющий контракт службы, которому должна соответствовать реализация клиента.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="6c5e6-121">Созданное клиентское приложение также содержит реализацию `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="6c5e6-122">Обратите внимание, что адрес и сведения о привязке не указываются ни в одном месте внутри реализации службы.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="6c5e6-123">Вам не нужно писать код для получения адреса или сведений о привязке из файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-123">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="6c5e6-124">*Svcutil.exe* также создает конфигурацию для клиента, использующего <xref:System.ServiceModel.WSHttpBinding> класс.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="6c5e6-125">Присвойте файлу конфигурации имя *App.config* при использовании Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-125">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="6c5e6-126">Создайте экземпляр класса `ClientCalculator` в приложении и вызовите операции службы.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="6c5e6-127">Скомпилируйте и запустите клиент.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="6c5e6-128">Пример</span><span class="sxs-lookup"><span data-stu-id="6c5e6-128">Example</span></span>

<span data-ttu-id="6c5e6-129">Некоторые привязки, предоставляемые системой, по умолчанию поддерживают надежные сеансы.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="6c5e6-130">К ним относятся следующие объекты.</span><span class="sxs-lookup"><span data-stu-id="6c5e6-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="6c5e6-131">Пример создания пользовательской привязки, поддерживающей надежные сеансы, см. [в разделе как создать настраиваемую привязку надежного сеанса с помощью протокола HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md).</span><span class="sxs-lookup"><span data-stu-id="6c5e6-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6c5e6-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6c5e6-132">See also</span></span>

- [<span data-ttu-id="6c5e6-133">Надежные сеансы</span><span class="sxs-lookup"><span data-stu-id="6c5e6-133">Reliable Sessions</span></span>](reliable-sessions.md)
