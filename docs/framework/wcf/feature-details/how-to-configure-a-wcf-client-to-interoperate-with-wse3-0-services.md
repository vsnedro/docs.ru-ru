---
title: Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 7dd50fcc07c6c090042cf87acb4aa5d2b5321a68
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84579583"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="f20f4-102">Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="f20f4-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="f20f4-103">Клиенты Windows Communication Foundation (WCF), совместимые с веб-службами, расширяют возможности 3,0 для служб Microsoft .NET (WSE), когда клиенты WCF настроены для использования версии спецификации WS-Addressing в августе 2004.</span><span class="sxs-lookup"><span data-stu-id="f20f4-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="f20f4-104">Настройка клиента WCF для взаимодействия с веб-службой WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="f20f4-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1. <span data-ttu-id="f20f4-105">Запустите [средство служебной программы метаданных ServiceModel (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать клиент WCF для веб-службы WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="f20f4-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="f20f4-106">Для веб-службы WSE создается клиентский класс WCF.</span><span class="sxs-lookup"><span data-stu-id="f20f4-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="f20f4-107">Дополнительные сведения о создании клиента WCF см. в разделе [инструкции. Создание клиента](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="f20f4-107">For details about creating a WCF client, see the [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="f20f4-108">Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="f20f4-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="f20f4-109">Следующий класс является частью примера [взаимодействия с WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) .</span><span class="sxs-lookup"><span data-stu-id="f20f4-109">The following class is part of the [Interoperating with WSE](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29) sample.</span></span>  
  
    1. <span data-ttu-id="f20f4-110">Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f20f4-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="f20f4-111">В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="f20f4-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. <span data-ttu-id="f20f4-112">Добавьте в класс свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, и параметры защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="f20f4-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="f20f4-113">В следующем примере кода определяются `SecurityAssertion` `RequireDerivedKeys` свойства,, `EstablishSecurityContext` и `MessageProtectionOrder` .</span><span class="sxs-lookup"><span data-stu-id="f20f4-113">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties.</span></span> <span data-ttu-id="f20f4-114">Они указывают на использование утверждений WSE, являются ли производные ключи обязательными, используются ли безопасные сеансы, требуются ли подтверждения подписей и параметры защиты сообщений соответственно.</span><span class="sxs-lookup"><span data-stu-id="f20f4-114">They specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <span data-ttu-id="f20f4-115">Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="f20f4-115">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="f20f4-116">В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="f20f4-116">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="f20f4-117">В коде клиентского приложения добавьте код для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="f20f4-117">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="f20f4-118">В следующем примере кода указывается, что клиент WCF должен использовать защиту и проверку подлинности сообщений, как определено в утверждении безопасности для использования WSE 3,0 `AnonymousForCertificate` .</span><span class="sxs-lookup"><span data-stu-id="f20f4-118">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="f20f4-119">Кроме того, требуются безопасные сеансы и производные ключи.</span><span class="sxs-lookup"><span data-stu-id="f20f4-119">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="f20f4-120">Пример</span><span class="sxs-lookup"><span data-stu-id="f20f4-120">Example</span></span>  
 <span data-ttu-id="f20f4-121">В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="f20f4-121">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="f20f4-122">Пользовательская привязка, которая называется `WseHttpBinding` , затем используется для указания свойств привязки для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="f20f4-122">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="f20f4-123">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f20f4-123">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- [<span data-ttu-id="f20f4-124">Взаимодействие с WSE</span><span class="sxs-lookup"><span data-stu-id="f20f4-124">Interoperating with WSE</span></span>](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms752257%28v=vs.90%29)
