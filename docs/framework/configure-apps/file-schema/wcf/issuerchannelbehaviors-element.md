---
title: Элемент <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: f7378673-8e9b-45b2-98d1-cf5dccdd8c40
no-loc:
- <system.serviceModel>
- <behaviors>
- <endpointBehaviors>
- <behavior>
- <clientCredentials>
- <issuedToken>
- <issuerChannelBehaviors>
- <dataContractSerializer>
ms.openlocfilehash: cbbfb9d3b5af47a360aa82cf837cd6749f61b641
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70893155"
---
# <a name="issuerchannelbehaviors-element"></a><span data-ttu-id="08fe5-102">Элемент \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="08fe5-102">\<issuerChannelBehaviors> Element</span></span>

<span data-ttu-id="08fe5-103">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) (определенную в конфигурации) для использования при взаимодействии с указанными службами маркеров службы.</span><span class="sxs-lookup"><span data-stu-id="08fe5-103">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors (defined in the configuration) to be used when communicating with the specified Service Token Services.</span></span> <span data-ttu-id="08fe5-104">Определенные поведения не могут включать [\<clientCredentials>](clientcredentials.md) элементы.</span><span class="sxs-lookup"><span data-stu-id="08fe5-104">The defined behaviors cannot include any [\<clientCredentials>](clientcredentials.md) elements.</span></span>

[\<configuration>](../configuration-element.md)\
&nbsp;&nbsp;[\<system.serviceModel>](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[\<behaviors>](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<endpointBehaviors>](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<behavior>](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<clientCredentials>](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[\<issuedToken>](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<issuerChannelBehaviors>

## <a name="syntax"></a><span data-ttu-id="08fe5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08fe5-105">Syntax</span></span>

```xml
<issuerChannelBehaviors>
  <add behaviorConfiguration="string"
       issuerAddress="string" />
</issuerChannelBehaviors>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="08fe5-106">Элементы и атрибуты</span><span class="sxs-lookup"><span data-stu-id="08fe5-106">Attributes and elements</span></span>

<span data-ttu-id="08fe5-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="08fe5-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="08fe5-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="08fe5-108">Attributes</span></span>

<span data-ttu-id="08fe5-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="08fe5-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="08fe5-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="08fe5-110">Child elements</span></span>

|<span data-ttu-id="08fe5-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="08fe5-111">Element</span></span>|<span data-ttu-id="08fe5-112">Описание</span><span class="sxs-lookup"><span data-stu-id="08fe5-112">Description</span></span>|
|-------------|-----------------|
|[\<add>](add-of-issuerchannelbehaviors.md)|<span data-ttu-id="08fe5-113">Добавляет поведение в коллекцию.</span><span class="sxs-lookup"><span data-stu-id="08fe5-113">Adds a behavior to the collection.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="08fe5-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="08fe5-114">Parent elements</span></span>

|<span data-ttu-id="08fe5-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="08fe5-115">Element</span></span>|<span data-ttu-id="08fe5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="08fe5-116">Description</span></span>|
|-------------|-----------------|
|[\<issuedToken>](issuedtoken.md)|<span data-ttu-id="08fe5-117">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="08fe5-117">Specifies a custom token used to authenticate a client to a service.</span></span>|

## <a name="remarks"></a><span data-ttu-id="08fe5-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="08fe5-118">Remarks</span></span>

<span data-ttu-id="08fe5-119">Этот элемент используется, когда для связи со службой необходимо любое поведение (кроме поведений, в которые включаются элементы `<clientCredentials>`).</span><span class="sxs-lookup"><span data-stu-id="08fe5-119">Use this element when any behaviors (other than behaviors that include `<clientCredentials>` elements) must be used to communicate with a service.</span></span> <span data-ttu-id="08fe5-120">Например, если [\<dataContractSerializer>](datacontractserializer-element.md) необходимо добавить элемент поведения.</span><span class="sxs-lookup"><span data-stu-id="08fe5-120">For example, if a [\<dataContractSerializer>](datacontractserializer-element.md) behavior element must be included.</span></span>

## <a name="see-also"></a><span data-ttu-id="08fe5-121">См. также</span><span class="sxs-lookup"><span data-stu-id="08fe5-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="08fe5-122">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="08fe5-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="08fe5-123">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="08fe5-123">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="08fe5-124">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="08fe5-124">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="08fe5-125">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="08fe5-125">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="08fe5-126">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="08fe5-126">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="08fe5-127">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="08fe5-127">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="08fe5-128">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="08fe5-128">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="08fe5-129">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="08fe5-129">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
