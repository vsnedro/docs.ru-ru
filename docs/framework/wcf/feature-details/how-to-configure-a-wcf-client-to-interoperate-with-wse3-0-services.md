---
title: Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3dadd7f1-d207-4ea5-a73b-3e8aa44407f8
ms.openlocfilehash: 1ebc4e145528c3025b0299ea7e421c248c28cdc0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556373"
---
# <a name="how-to-configure-a-wcf-client-to-interoperate-with-wse30-services"></a><span data-ttu-id="47d72-102">Практическое руководство. Настройка клиента WCF для взаимодействия со службами WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="47d72-102">How to: Configure a WCF Client to interoperate with WSE3.0 Services</span></span>
<span data-ttu-id="47d72-103">Клиенты Windows Communication Foundation (WCF), совместимые с веб-службами, расширяют возможности 3,0 для служб Microsoft .NET (WSE), когда клиенты WCF настроены для использования версии спецификации WS-Addressing в августе 2004.</span><span class="sxs-lookup"><span data-stu-id="47d72-103">Windows Communication Foundation (WCF) clients are wire-level compatible with Web Services Enhancements 3.0 for Microsoft .NET (WSE) services when WCF clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span>  
  
### <a name="to-configure-a-wcf-client-to-interoperate-with-a-wse-30-web-service"></a><span data-ttu-id="47d72-104">Настройка клиента WCF для взаимодействия с веб-службой WSE 3.0</span><span class="sxs-lookup"><span data-stu-id="47d72-104">To configure a WCF client to interoperate with a WSE 3.0 Web service</span></span>  
  
1. <span data-ttu-id="47d72-105">Запустите [средство служебной программы метаданных ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , чтобы создать клиент WCF для веб-службы WSE 3,0.</span><span class="sxs-lookup"><span data-stu-id="47d72-105">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to create a WCF client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="47d72-106">Для веб-службы WSE создается клиентский класс WCF.</span><span class="sxs-lookup"><span data-stu-id="47d72-106">For a WSE Web service, a WCF client class is created.</span></span>  
  
     <span data-ttu-id="47d72-107">Дополнительные сведения о создании клиента WCF см. в разделе [инструкции. Создание клиента](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="47d72-107">For details about creating a WCF client, see the [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>  
  
2. <span data-ttu-id="47d72-108">Создайте класс, представляющий привязку, которая может обмениваться данными с веб-службами WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="47d72-108">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="47d72-109">Следующий класс является частью примера [взаимодействия с WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) .</span><span class="sxs-lookup"><span data-stu-id="47d72-109">The following class is part of the [Interoperating with WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90)) sample.</span></span>  
  
    1. <span data-ttu-id="47d72-110">Создайте класс, производный от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="47d72-110">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="47d72-111">В следующем примере кода создается класс с именем `WseHttpBinding`, наследуемый от класса <xref:System.ServiceModel.Channels.Binding>.</span><span class="sxs-lookup"><span data-stu-id="47d72-111">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2. <span data-ttu-id="47d72-112">Добавьте в класс свойства, задающие готовое к использованию утверждение WSE, требуются ли производные ключи, используются ли безопасные сеансы, требуется ли подтверждение подписей, и параметры защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="47d72-112">Add properties to the class that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span>  
  
         <span data-ttu-id="47d72-113">В следующем примере кода определяются `SecurityAssertion` `RequireDerivedKeys` свойства,, `EstablishSecurityContext` и `MessageProtectionOrder` .</span><span class="sxs-lookup"><span data-stu-id="47d72-113">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties.</span></span> <span data-ttu-id="47d72-114">Они указывают на использование утверждений WSE, являются ли производные ключи обязательными, используются ли безопасные сеансы, требуются ли подтверждения подписей и параметры защиты сообщений соответственно.</span><span class="sxs-lookup"><span data-stu-id="47d72-114">They specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3. <span data-ttu-id="47d72-115">Переопределите метод <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="47d72-115">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="47d72-116">В следующем примере кода транспорт, кодирование сообщений и параметры защиты сообщений задаются получением значений свойств `SecurityAssertion` и `MessageProtectionOrder`.</span><span class="sxs-lookup"><span data-stu-id="47d72-116">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3. <span data-ttu-id="47d72-117">В коде клиентского приложения добавьте код для задания свойств привязки.</span><span class="sxs-lookup"><span data-stu-id="47d72-117">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="47d72-118">В следующем примере кода указывается, что клиент WCF должен использовать защиту и проверку подлинности сообщений, как определено в утверждении безопасности для использования WSE 3,0 `AnonymousForCertificate` .</span><span class="sxs-lookup"><span data-stu-id="47d72-118">The following code example specifies that the WCF client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="47d72-119">Кроме того, требуются безопасные сеансы и производные ключи.</span><span class="sxs-lookup"><span data-stu-id="47d72-119">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="47d72-120">Пример</span><span class="sxs-lookup"><span data-stu-id="47d72-120">Example</span></span>  
 <span data-ttu-id="47d72-121">В следующем примере кода определяется пользовательская привязка, предоставляющая свойства, соответствующие свойствам готового к использованию утверждения безопасности WSE 3.0.</span><span class="sxs-lookup"><span data-stu-id="47d72-121">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="47d72-122">Пользовательская привязка, которая называется `WseHttpBinding` , затем используется для указания свойств привязки для клиента WCF.</span><span class="sxs-lookup"><span data-stu-id="47d72-122">The custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a WCF client.</span></span>  

[!code-csharp[c_WCFClientToWSEService#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#0)]
[!code-vb[c_WCFClientToWSEService#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="47d72-123">См. также</span><span class="sxs-lookup"><span data-stu-id="47d72-123">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <span data-ttu-id="47d72-124">[Взаимодействие с WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="47d72-124">[Interoperating with WSE](/previous-versions/dotnet/netframework-3.5/ms752257(v=vs.90))</span></span>
