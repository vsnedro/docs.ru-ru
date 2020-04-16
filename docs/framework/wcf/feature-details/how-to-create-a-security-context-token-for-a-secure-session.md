---
title: Практическое руководство. Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
ms.openlocfilehash: 4e91580035d4de23ae90cd0d59a08f321ae70a1c
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464137"
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="8ed2d-102">Практическое руководство. Как создать маркер контекста безопасности с отслеживанием состояния для безопасного сеанса</span><span class="sxs-lookup"><span data-stu-id="8ed2d-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="8ed2d-103">При использовании в безопасном сеансе маркера контекста безопасности (SCT) с отслеживанием состояния сеанс может сохраняться и при перезапуске службы.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="8ed2d-104">Например, если в безопасном сеансе используется маркер SCT без учета состояния, то при сбросе служб IIS данные сеанса, связанного со службой, будут потеряны.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="8ed2d-105">В состав данных сеанса входит кэш маркера SCT.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="8ed2d-106">Поэтому в следующий раз, когда клиент отправляет в службу маркер SCT без учета состояния, возвращается ошибка, так как невозможно извлечь ключ, связанный с этим маркером SCT.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="8ed2d-107">Однако если используется маркер SCT с отслеживанием состояния, то ключ, связанный с маркером SCT, содержится в этом маркере SCT.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="8ed2d-108">Так как ключ содержится в маркере SCT и, следовательно, в сообщении, перезапуск службы не влияет на безопасный сеанс.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="8ed2d-109">По умолчанию Фонд связи Windows (WCF) использует SCTбеза без состояния в безопасном сеансе.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-109">By default, Windows Communication Foundation (WCF) uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="8ed2d-110">В этом разделе описывается, как использовать в безопасном сеансе маркеры SCT с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ed2d-111">Маркеры SCT с отслеживанием состояния не могут использоваться в безопасном сеансе, связанном с контрактом, унаследованным от <xref:System.ServiceModel.Channels.IDuplexChannel>.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ed2d-112">Для приложений, использующих в безопасных сеансах маркеры SCT с отслеживанием состояния, идентификатором потока для службы должна быть учетная запись пользователя, имеющая связанный с ней профиль пользователя.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="8ed2d-113">Если служба запущена с учетной записью, не имеющей профиля пользователя (например, `Local Service`), возможно возникновение исключения.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ed2d-114">Если в ОС Windows XP требуется олицетворение, следует использовать безопасный сеанс без маркера SCT с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="8ed2d-115">При использовании маркеров SCT с отслеживанием состояния вместе с олицетворением возникает исключение <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="8ed2d-116">Для получения дополнительной информации [см.](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="8ed2d-116">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="8ed2d-117">Использование маркеров SCT с отслеживанием состояния в безопасном сеансе</span><span class="sxs-lookup"><span data-stu-id="8ed2d-117">To use stateful SCTs in a secure session</span></span>  
  
- <span data-ttu-id="8ed2d-118">Создайте пользовательскую привязку, которая задает, что сообщения SOAP защищаются безопасным сеансом, использующим маркер SCT с отслеживанием состояния.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1. <span data-ttu-id="8ed2d-119">Определите пользовательский привязку, добавив [ \<пользовательский>в](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) файл конфигурации для службы.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-119">Define a custom binding, by adding a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        </customBinding>
        ```  
  
    2. <span data-ttu-id="8ed2d-120">Добавьте [ \<связывающий элемент>](../../configure-apps/file-schema/wcf/bindings.md) ребенка в [ \<пользовательский>Binding. ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ed2d-120">Add a [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="8ed2d-121">Укажите имя привязки, задав для атрибута `name` имя, уникальное в пределах этого файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        </binding>
        ```  
  
    3. <span data-ttu-id="8ed2d-122">Укажите режим проверки подлинности для сообщений, отправленных в эту службу и из нее, добавив элемент [ \<безопасности>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) ребенка в [ \<пользовательскийОбязательный>. ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="8ed2d-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="8ed2d-123">Укажите, что используется безопасный сеанс, задав для атрибута `authenticationMode` значение `SecureConversation`.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="8ed2d-124">Укажите, что используются маркеры SCT с отслеживанием состояния, задав для атрибута `requireSecurityContextCancellation` значение `false`.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">
        </security>
        ```  
  
    4. <span data-ttu-id="8ed2d-125">Укажите, как клиент проверяется на подлинность во время создания безопасного сеанса, добавляя в [ \<>безопасности ](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [ \<элемент защищенного разговора>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) ребенка.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="8ed2d-126">Укажите, как производится проверка подлинности клиента, задав атрибут `authenticationMode`.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5. <span data-ttu-id="8ed2d-127">Укажите кодирование сообщения, добавив элемент кодирования, например [ \<>textMessageEncoding. ](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)</span><span class="sxs-lookup"><span data-stu-id="8ed2d-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6. <span data-ttu-id="8ed2d-128">Укажите транспорт, добавив транспортный элемент, такой как [ \<httpTransport>. ](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)</span><span class="sxs-lookup"><span data-stu-id="8ed2d-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="8ed2d-129">В следующем примере кода с помощью конфигурации задается пользовательская привязка, которая может использоваться сообщениями с маркерами SCT с отслеживанием состояния в безопасном сеансе.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="8ed2d-130">Пример</span><span class="sxs-lookup"><span data-stu-id="8ed2d-130">Example</span></span>  
 <span data-ttu-id="8ed2d-131">В следующем примере кода создается пользовательская привязка, которая использует режим проверки подлинности <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> для начальной загрузки безопасного сеанса.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="8ed2d-132">Когда аутентификация Windows используется в сочетании с stateful <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> SCT, WCF не заполняет свойство с идентификацией фактического вызывающего абонента, но вместо этого устанавливает свойство к анонимности.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-132">When Windows authentication is used in combination with a stateful SCT, WCF does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="8ed2d-133">Поскольку безопасность WCF должна повторно создавать содержимое контекста безопасности службы для каждого запроса от входящего SCT, сервер не отслеживает сеанс безопасности в памяти.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-133">Because WCF security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="8ed2d-134">Поскольку выполнить сериализацию экземпляра <xref:System.Security.Principal.WindowsIdentity> в маркер SCT невозможно, свойство <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> возвращает анонимный идентификатор.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="8ed2d-135">Следующая конфигурация демонстрирует это расширение функциональности.</span><span class="sxs-lookup"><span data-stu-id="8ed2d-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
        </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ed2d-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8ed2d-136">See also</span></span>

- [<span data-ttu-id="8ed2d-137">\<обычайОбязательный></span><span class="sxs-lookup"><span data-stu-id="8ed2d-137">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
