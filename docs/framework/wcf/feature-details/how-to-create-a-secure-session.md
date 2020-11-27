---
title: Практическое руководство. Создание сеанса безопасности
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
ms.openlocfilehash: f6fb73653add7362e8c8452e75be802395ffc3cd
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96286530"
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="26cc8-102">Практическое руководство. Создание сеанса безопасности</span><span class="sxs-lookup"><span data-stu-id="26cc8-102">How to: Create a Secure Session</span></span>

<span data-ttu-id="26cc8-103">За исключением [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) привязки, предоставляемые системой привязки в Windows Communication Foundation (WCF) автоматически используют защищенные сеансы при включенной безопасности сообщений.</span><span class="sxs-lookup"><span data-stu-id="26cc8-103">With the exception of the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in Windows Communication Foundation (WCF) automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="26cc8-104">По умолчанию безопасные сеансы не сохраняются на перезапускаемом веб-сервере.</span><span class="sxs-lookup"><span data-stu-id="26cc8-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="26cc8-105">После установления безопасного сеанса клиент и служба кэшируют ключ, связанный с безопасным сеансом.</span><span class="sxs-lookup"><span data-stu-id="26cc8-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="26cc8-106">При обмене сообщениями происходит только обмен идентификатором кэшированного ключа.</span><span class="sxs-lookup"><span data-stu-id="26cc8-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="26cc8-107">При перезапуске веб-сервера кэш также перезапускается, следовательно, веб-сервер не может извлечь кэшированный ключ для идентификатора.</span><span class="sxs-lookup"><span data-stu-id="26cc8-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="26cc8-108">В этом случае исключение передается назад клиенту.</span><span class="sxs-lookup"><span data-stu-id="26cc8-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="26cc8-109">Безопасные сеансы, использующие токен контекста безопасности с отслеживанием состояния (SCT), сохраняются при перезапуске веб-сервера.</span><span class="sxs-lookup"><span data-stu-id="26cc8-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> <span data-ttu-id="26cc8-110">Дополнительные сведения об использовании SCT с отслеживанием состояния в безопасном сеансе см. в разделе [инструкции. Создание маркера контекста безопасности для безопасного сеанса](how-to-create-a-security-context-token-for-a-secure-session.md).</span><span class="sxs-lookup"><span data-stu-id="26cc8-110">For more information about using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="26cc8-111">Задание использования службой безопасных сеансов с помощью одной из предоставляемых системой привязок</span><span class="sxs-lookup"><span data-stu-id="26cc8-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
- <span data-ttu-id="26cc8-112">Настройте службу на использование предоставляемой системой привязки, поддерживающей безопасность сообщений.</span><span class="sxs-lookup"><span data-stu-id="26cc8-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="26cc8-113">За исключением [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) привязки, когда предоставляемые системой привязки настроены для использования безопасности сообщений, WCF автоматически использует защищенные сеансы.</span><span class="sxs-lookup"><span data-stu-id="26cc8-113">With the exception of the [\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, WCF automatically uses secure sessions.</span></span> <span data-ttu-id="26cc8-114">В следующей таблице перечислены предоставляемые системой привязки, поддерживающие безопасность сообщений, и указано, является ли безопасность сообщений механизмом безопасности по умолчанию для данной привязки.</span><span class="sxs-lookup"><span data-stu-id="26cc8-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="26cc8-115">Предоставляемая системой привязка</span><span class="sxs-lookup"><span data-stu-id="26cc8-115">System-provided binding</span></span>|<span data-ttu-id="26cc8-116">Элемент конфигурации</span><span class="sxs-lookup"><span data-stu-id="26cc8-116">Configuration element</span></span>|<span data-ttu-id="26cc8-117">Безопасность сообщений включена по умолчанию</span><span class="sxs-lookup"><span data-stu-id="26cc8-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="26cc8-118">Нет</span><span class="sxs-lookup"><span data-stu-id="26cc8-118">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="26cc8-119">Да</span><span class="sxs-lookup"><span data-stu-id="26cc8-119">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="26cc8-120">Да</span><span class="sxs-lookup"><span data-stu-id="26cc8-120">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="26cc8-121">Да</span><span class="sxs-lookup"><span data-stu-id="26cc8-121">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="26cc8-122">Нет</span><span class="sxs-lookup"><span data-stu-id="26cc8-122">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../../configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="26cc8-123">Нет</span><span class="sxs-lookup"><span data-stu-id="26cc8-123">No</span></span>|  
  
     <span data-ttu-id="26cc8-124">В следующем примере кода используется конфигурация для указания привязки с именем, `wsHttpBinding_Calculator` которая использует [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) , безопасность сообщений и защищенные сеансы.</span><span class="sxs-lookup"><span data-stu-id="26cc8-124">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="26cc8-125">В следующем примере кода указывается, что [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) для защиты службы используются, безопасность сообщений и безопасные сеансы `secureCalculator` .</span><span class="sxs-lookup"><span data-stu-id="26cc8-125">The following code example specifies that the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    > <span data-ttu-id="26cc8-126">Защищенные сеансы можно отключить для, [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) задав `establishSecurityContext` для атрибута значение `false` .</span><span class="sxs-lookup"><span data-stu-id="26cc8-126">Secure sessions can be turned off for the [\<wsHttpBinding>](../../configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="26cc8-127">Безопасные сеансы для других предоставляемых системой привязок можно отключить, только создав пользовательскую привязку.</span><span class="sxs-lookup"><span data-stu-id="26cc8-127">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="26cc8-128">Задание использования службой безопасных сеансов с помощью пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="26cc8-128">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
- <span data-ttu-id="26cc8-129">Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом.</span><span class="sxs-lookup"><span data-stu-id="26cc8-129">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     <span data-ttu-id="26cc8-130">Дополнительные сведения о создании пользовательской привязки см. в разделе [инструкции. Настройка привязки System-Provided](../extending/how-to-customize-a-system-provided-binding.md).</span><span class="sxs-lookup"><span data-stu-id="26cc8-130">For more information about creating a custom binding, see [How to: Customize a System-Provided Binding](../extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="26cc8-131">В следующем примере кода с помощью конфигурации задается пользовательская привязка для обмена сообщениями с использованием безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="26cc8-131">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="26cc8-132">В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> для начальной загрузки безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="26cc8-132">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="26cc8-133">См. также</span><span class="sxs-lookup"><span data-stu-id="26cc8-133">See also</span></span>

- [<span data-ttu-id="26cc8-134">Общие сведения о привязках WCF</span><span class="sxs-lookup"><span data-stu-id="26cc8-134">WCF Bindings Overview</span></span>](../bindings-overview.md)
