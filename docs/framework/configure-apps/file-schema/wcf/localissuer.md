---
title: <localIssuer>
ms.date: 03/30/2017
ms.assetid: 26bdd0df-0e7d-4b9e-bbeb-f28c53769385
ms.openlocfilehash: e08d2c0b42cfd8e302223915f0256f8cb2d1468b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204961"
---
# \<localIssuer>

<span data-ttu-id="f109e-101">Указывает адрес и привязку локального издателя, используемого для получения маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="f109e-101">Specifies the address and binding of the local issuer to be used to obtain a security token.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<localIssuer>**  
  
## <a name="syntax"></a><span data-ttu-id="f109e-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f109e-102">Syntax</span></span>  
  
```xml  
<localIssuer address="String"
             binding="String"
             bindingConfiguration="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f109e-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f109e-103">Attributes and Elements</span></span>  

 <span data-ttu-id="f109e-104">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f109e-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f109e-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f109e-105">Attributes</span></span>  
  
|<span data-ttu-id="f109e-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f109e-106">Attribute</span></span>|<span data-ttu-id="f109e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f109e-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f109e-108">address</span><span class="sxs-lookup"><span data-stu-id="f109e-108">address</span></span>|<span data-ttu-id="f109e-109">Обязательная строка.</span><span class="sxs-lookup"><span data-stu-id="f109e-109">Required string.</span></span> <span data-ttu-id="f109e-110">Указывает универсальный код ресурса (URI) локального издателя.</span><span class="sxs-lookup"><span data-stu-id="f109e-110">Specifies the URI of the local issuer.</span></span>|  
|<span data-ttu-id="f109e-111">binding</span><span class="sxs-lookup"><span data-stu-id="f109e-111">binding</span></span>|<span data-ttu-id="f109e-112">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="f109e-112">Optional string.</span></span> <span data-ttu-id="f109e-113">Одна из привязок, предоставляемых системой.</span><span class="sxs-lookup"><span data-stu-id="f109e-113">One of the system-provided bindings.</span></span> <span data-ttu-id="f109e-114">Список см. в разделе [привязки, предоставляемые системой](../../../wcf/system-provided-bindings.md).</span><span class="sxs-lookup"><span data-stu-id="f109e-114">For a list, see [System-Provided Bindings](../../../wcf/system-provided-bindings.md).</span></span>|  
|<span data-ttu-id="f109e-115">bindingConfiguration</span><span class="sxs-lookup"><span data-stu-id="f109e-115">bindingConfiguration</span></span>|<span data-ttu-id="f109e-116">Необязательная строка.</span><span class="sxs-lookup"><span data-stu-id="f109e-116">Optional string.</span></span> <span data-ttu-id="f109e-117">Указывает конфигурацию привязки в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f109e-117">Specifies a binding configuration found in the configuration file.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f109e-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f109e-118">Child Elements</span></span>  
  
|<span data-ttu-id="f109e-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="f109e-119">Element</span></span>|<span data-ttu-id="f109e-120">Описание</span><span class="sxs-lookup"><span data-stu-id="f109e-120">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="f109e-121">Указывает идентификационные данные для локального издателя.</span><span class="sxs-lookup"><span data-stu-id="f109e-121">Specifies identity information for the local issuer.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="f109e-122">Коллекция заголовков адреса, требуемых для правильного обращения к локальному издателю.</span><span class="sxs-lookup"><span data-stu-id="f109e-122">A collection of address headers that are required in order to correctly address the local issuer.</span></span> <span data-ttu-id="f109e-123">Заголовок в эту коллекцию можно добавить с помощью ключевого слова `add`.</span><span class="sxs-lookup"><span data-stu-id="f109e-123">You can use the `add` keyword to add a header to this collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f109e-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f109e-124">Parent Elements</span></span>  
  
|<span data-ttu-id="f109e-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="f109e-125">Element</span></span>|<span data-ttu-id="f109e-126">Описание</span><span class="sxs-lookup"><span data-stu-id="f109e-126">Description</span></span>|  
|-------------|-----------------|  
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="f109e-127">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="f109e-127">Specifies a custom token used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f109e-128">Remarks</span><span class="sxs-lookup"><span data-stu-id="f109e-128">Remarks</span></span>  

 <span data-ttu-id="f109e-129">При получении маркера от службы маркеров безопасности (STS) в клиентском приложении должны быть заданы адрес и привязка для установления соединения с STS.</span><span class="sxs-lookup"><span data-stu-id="f109e-129">When obtaining an issued token from a Security Token Service (STS), the client application must be configured with the address and binding to use to communicate with the STS.</span></span> <span data-ttu-id="f109e-130">Если <xref:System.ServiceModel.WSFederationHttpBinding> компонент не предоставляет URL-адрес для службы маркеров безопасности или если адресом издателя Федеративной привязки является `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` или `null` , канал Windows Communication Foundation клиента (WCF) использует значения, заданные параметром, `address` и, `binding` чтобы взаимодействовать с STS для получения выданного маркера.</span><span class="sxs-lookup"><span data-stu-id="f109e-130">When the <xref:System.ServiceModel.WSFederationHttpBinding> does not supply a URL for the security token service, or when the issuer address of a federated binding is `http://schemas.microsoft.com/2005/12/ServiceModel/Addressing/Anonymous` or `null`, the client's Windows Communication Foundation (WCF) channel uses the values specified by `address` and `binding` to communicate with the STS to obtain the issued token.</span></span> <span data-ttu-id="f109e-131">Дополнительные сведения о настройке локального издателя см. в разделе [как настроить локальный издатель](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="f109e-131">For more information on configuring a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f109e-132">Пример</span><span class="sxs-lookup"><span data-stu-id="f109e-132">Example</span></span>  

 <span data-ttu-id="f109e-133">В следующем примере устанавливаются атрибуты `address`, `binding` и `bindingConfiguration` элемента `localIssuer`.</span><span class="sxs-lookup"><span data-stu-id="f109e-133">The following example sets the `address`, `binding`, and `bindingConfiguration` attributes of a `localIssuer` element.</span></span>  
  
```xml  
<system.serviceModel>
  <behaviors>
    <endpointBehaviors>
      <behavior name="MyEndpointBehavior">
        <clientCredentials>
          <issuedToken cacheIssuedTokens="false"
                       defaultKeyEntropyMode="ClientEntropy">
            <localIssuer address="net.tcp://cohowinery/tokens"
                         binding="netTcpBinding"
                         bindingConfiguration="myTcpBindingConfig" />
          </issuedToken>
        </clientCredentials>
      </behavior>
    </endpointBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="f109e-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f109e-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.LocalIssuer%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersEndpointAddressElement>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="f109e-135">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="f109e-135">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f109e-136">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="f109e-136">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="f109e-137">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="f109e-137">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f109e-138">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="f109e-138">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="f109e-139">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="f109e-139">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="f109e-140">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f109e-140">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="f109e-141">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="f109e-141">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="f109e-142">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="f109e-142">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="f109e-143">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="f109e-143">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
