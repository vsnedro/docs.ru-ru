---
title: <add> из <issuerChannelBehaviors>
ms.date: 03/30/2017
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
ms.openlocfilehash: cf7ac2691ad1c641352a8047373ced538b19e983
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70398333"
---
# <a name="add-of-issuerchannelbehaviors"></a><span data-ttu-id="3795b-102">\<add> из \<issuerChannelBehaviors></span><span class="sxs-lookup"><span data-stu-id="3795b-102">\<add> of \<issuerChannelBehaviors></span></span>

<span data-ttu-id="3795b-103">Добавляет поведение конечной точки, которое должно использоваться при взаимодействии со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3795b-103">Adds an endpoint behavior to be used when communicating with an STS.</span></span>

> [!NOTE]
> <span data-ttu-id="3795b-104">Если какое-либо поведение конечной точки содержит [\<clientCredentials>](clientcredentials.md) элемент, будет создано исключение.</span><span class="sxs-lookup"><span data-stu-id="3795b-104">If any endpoint behavior contains a [\<clientCredentials>](clientcredentials.md) element, an exception will be thrown.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedToken>**](issuedtoken.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuerChannelBehaviors>**](issuerchannelbehaviors-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**  

## <a name="syntax"></a><span data-ttu-id="3795b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3795b-105">Syntax</span></span>

```xml
<add issuerAddress="string"
     behaviorConfiguration="string" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="3795b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3795b-106">Attributes and Elements</span></span>

<span data-ttu-id="3795b-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3795b-107">The following sections describe attributes, child elements, and parent elements</span></span>

### <a name="attributes"></a><span data-ttu-id="3795b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3795b-108">Attributes</span></span>

|<span data-ttu-id="3795b-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3795b-109">Attribute</span></span>|<span data-ttu-id="3795b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="3795b-110">Description</span></span>|
|---------------|-----------------|
|<span data-ttu-id="3795b-111">issuerAddress</span><span class="sxs-lookup"><span data-stu-id="3795b-111">issuerAddress</span></span>|<span data-ttu-id="3795b-112">Универсальный код ресурса (URI) издателя маркера безопасности, с которым осуществляется взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="3795b-112">The URI of the security token issuer to communicate with.</span></span>|
|<span data-ttu-id="3795b-113">behaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="3795b-113">behaviorConfiguration</span></span>|<span data-ttu-id="3795b-114">Имя поведения конечной точки, определенное в том же файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3795b-114">The name of an endpoint behavior defined in the same configuration file.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3795b-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3795b-115">Child Elements</span></span>

<span data-ttu-id="3795b-116">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3795b-116">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="3795b-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3795b-117">Parent Elements</span></span>

|<span data-ttu-id="3795b-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="3795b-118">Element</span></span>|<span data-ttu-id="3795b-119">Описание</span><span class="sxs-lookup"><span data-stu-id="3795b-119">Description</span></span>|
|-------------|-----------------|
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="3795b-120">Содержит коллекцию поведений конечной точки клиента Windows Communication Foundation (WCF) для использования при взаимодействии с указанными службами маркеров службы.</span><span class="sxs-lookup"><span data-stu-id="3795b-120">Contains a collection of Windows Communication Foundation (WCF) client endpoint behaviors to be used when communicating with the specified Service Token Services.</span></span>|

## <a name="remarks"></a><span data-ttu-id="3795b-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="3795b-121">Remarks</span></span>

<span data-ttu-id="3795b-122">`issuerAddress` содержит URI службы токенов безопасности, с которым клиент хочет обмениваться данными.</span><span class="sxs-lookup"><span data-stu-id="3795b-122">`issuerAddress` contains the URI of the Security Token Service that the client wants to communicate with.</span></span> <span data-ttu-id="3795b-123">`behaviorConfiguration`Указывает на поведение конечной точки, используемое приложением в каналах, созданных Windows Communication Foundation (WCF) для получения выданных маркеров от служб маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="3795b-123">`behaviorConfiguration` points to an endpoint behavior that the application uses in the channels created by Windows Communication Foundation (WCF) to get the issued tokens from the Security Token Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="3795b-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3795b-124">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>
- <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>
- [<span data-ttu-id="3795b-125">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="3795b-125">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="3795b-126">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="3795b-126">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="3795b-127">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="3795b-127">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="3795b-128">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3795b-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3795b-129">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="3795b-129">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="3795b-130">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="3795b-130">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="3795b-131">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="3795b-131">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="3795b-132">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="3795b-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)
