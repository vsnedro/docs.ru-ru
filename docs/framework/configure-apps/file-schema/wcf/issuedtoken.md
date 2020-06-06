---
title: <issuedToken>
ms.date: 03/30/2017
ms.assetid: b6eae4b7-a6cd-4e1a-b0f6-f407022550b0
ms.openlocfilehash: 56439748926ada642018f48a5787634a50d0f180
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "72846862"
---
# \<issuedToken>
<span data-ttu-id="a83ad-101">Задает пользовательский маркер, используемый для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="a83ad-101">Specifies a custom token used to authenticate a client to a service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuedToken>**  
  
## <a name="syntax"></a><span data-ttu-id="a83ad-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a83ad-102">Syntax</span></span>  
  
```xml  
<issuedToken cacheIssuedTokens="Boolean"
             defaultKeyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"
             issuedTokenRenewalThresholdPercentage = "0 to 100"
             issuerChannelBehaviors="String"
             localIssuerChannelBehaviors="String"
             maxIssuedTokenCachingTime="TimeSpan">
</issuedToken>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a83ad-103">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a83ad-103">Attributes and Elements</span></span>  
 <span data-ttu-id="a83ad-104">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a83ad-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a83ad-105">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a83ad-105">Attributes</span></span>  
  
|<span data-ttu-id="a83ad-106">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a83ad-106">Attribute</span></span>|<span data-ttu-id="a83ad-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="a83ad-107">Description</span></span>|  
|---------------|-----------------|  
|`cacheIssuedTokens`|<span data-ttu-id="a83ad-108">Дополнительный логический атрибут, указывающий, выполняется ли кэширование маркеров.</span><span class="sxs-lookup"><span data-stu-id="a83ad-108">Optional Boolean attribute that specifies whether tokens are cached.</span></span> <span data-ttu-id="a83ad-109">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="a83ad-109">The default is `true`.</span></span>|  
|`defaultKeyEntropyMode`|<span data-ttu-id="a83ad-110">Дополнительный строковый атрибут, указывающий, какие случайные значения (показатели энтропии) используются для операций «рукопожатия».</span><span class="sxs-lookup"><span data-stu-id="a83ad-110">Optional string attribute that specifies which random values (entropies) are used for handshake operations.</span></span> <span data-ttu-id="a83ad-111">Допустимы следующие значения: `ClientEntropy`, `ServerEntropy` и `CombinedEntropy`. Значение по умолчанию - `CombinedEntropy`.</span><span class="sxs-lookup"><span data-stu-id="a83ad-111">Values include `ClientEntropy`, `ServerEntropy`, and `CombinedEntropy`, The default is `CombinedEntropy`.</span></span> <span data-ttu-id="a83ad-112">Это атрибут типа <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span><span class="sxs-lookup"><span data-stu-id="a83ad-112">This attribute is of type <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.</span></span>|  
|`issuedTokenRenewalThresholdPercentage`|<span data-ttu-id="a83ad-113">Дополнительный целочисленный атрибут, задающий время в процентах от срока действия (предоставляемого издателем маркера), которое может пройти до обновления маркера.</span><span class="sxs-lookup"><span data-stu-id="a83ad-113">Optional integer attribute that specifies the percentage of a valid time frame (supplied by the token issuer) that can pass before a token is renewed.</span></span> <span data-ttu-id="a83ad-114">Диапазон значений: 0–100.</span><span class="sxs-lookup"><span data-stu-id="a83ad-114">Values are from 0 to 100.</span></span> <span data-ttu-id="a83ad-115">Значение по умолчанию, равное 60, указывает, что попытка возобновления предпринимается по истечении 60% времени.</span><span class="sxs-lookup"><span data-stu-id="a83ad-115">The default is 60, which specifies 60% of the time passes before a renewal is attempted.</span></span>|  
|`issuerChannelBehaviors`|<span data-ttu-id="a83ad-116">Дополнительный атрибут, определяющий поведения канала во время связи с издателем.</span><span class="sxs-lookup"><span data-stu-id="a83ad-116">Optional attribute that specifies the channel behaviors to use when communicating with the issuer.</span></span>|  
|`localIssuerChannelBehaviors`|<span data-ttu-id="a83ad-117">Дополнительный атрибут, определяющий поведения канала во время связи с локальным издателем.</span><span class="sxs-lookup"><span data-stu-id="a83ad-117">Optional attribute that specifies the channel behaviors to use when communicating with the local issuer.</span></span>|  
|`maxIssuedTokenCachingTime`|<span data-ttu-id="a83ad-118">Дополнительный атрибут Timespan, задающий промежуток времени, в течение которого выданные маркеры сохраняются в кэше, если время не указывается издателем маркера (службой маркеров безопасности).</span><span class="sxs-lookup"><span data-stu-id="a83ad-118">Optional Timespan attribute that specifies the duration that issued tokens are cached when the token issuer (an STS) does not specify a time.</span></span> <span data-ttu-id="a83ad-119">Значение по умолчанию — "10675199.02:48:05.4775807".</span><span class="sxs-lookup"><span data-stu-id="a83ad-119">The default is "10675199.02:48:05.4775807."</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a83ad-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a83ad-120">Child Elements</span></span>  
  
|<span data-ttu-id="a83ad-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="a83ad-121">Element</span></span>|<span data-ttu-id="a83ad-122">Описание</span><span class="sxs-lookup"><span data-stu-id="a83ad-122">Description</span></span>|  
|-------------|-----------------|  
|[\<localIssuer>](localissuer.md)|<span data-ttu-id="a83ad-123">Определяет адрес локального издателя маркера и привязку, используемую для взаимодействия с конечной точкой.</span><span class="sxs-lookup"><span data-stu-id="a83ad-123">Specifies the address of the local issuer of the token and the binding used to communicate with the endpoint.</span></span>|  
|[\<issuerChannelBehaviors>](issuerchannelbehaviors-element.md)|<span data-ttu-id="a83ad-124">Задает поведения конечной точки, используемое при связи с локальным издателем.</span><span class="sxs-lookup"><span data-stu-id="a83ad-124">Specifies the endpoint behaviors to use when contacting a local issuer.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a83ad-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a83ad-125">Parent Elements</span></span>  
  
|<span data-ttu-id="a83ad-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="a83ad-126">Element</span></span>|<span data-ttu-id="a83ad-127">Описание</span><span class="sxs-lookup"><span data-stu-id="a83ad-127">Description</span></span>|  
|-------------|-----------------|  
|[\<clientCredentials>](clientcredentials.md)|<span data-ttu-id="a83ad-128">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="a83ad-128">Specifies the credentials used to authenticate a client to a service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a83ad-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="a83ad-129">Remarks</span></span>  
 <span data-ttu-id="a83ad-130">Выданный маркер представляет собой пользовательские учетные данные, используемые, например, при проверке подлинности с помощью службы маркеров безопасности при федеративном доступе.</span><span class="sxs-lookup"><span data-stu-id="a83ad-130">An issued token is a custom credential type used, for example, when authenticating with a Secure Token Service (STS) in a federated scenario.</span></span> <span data-ttu-id="a83ad-131">По умолчанию используется маркер SAML.</span><span class="sxs-lookup"><span data-stu-id="a83ad-131">By default, the token is a SAML token.</span></span> <span data-ttu-id="a83ad-132">Дополнительные сведения см. в статьях [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md), [Федерация и выданные токены](../../../wcf/feature-details/federation-and-issued-tokens.md).</span><span class="sxs-lookup"><span data-stu-id="a83ad-132">For more information, see [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md), and [Federation and Issued Tokens](../../../wcf/feature-details/federation-and-issued-tokens.md).</span></span>  
  
 <span data-ttu-id="a83ad-133">Этот раздел содержит элементы, используемые для настройки локального издателя маркеров, или поведения, используемые при работе со службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="a83ad-133">This section contains the elements used to configure a local issuer of tokens, or behaviors used with an security token service.</span></span> <span data-ttu-id="a83ad-134">Инструкции по настройке клиента для использования локального издателя см. [в разделе как настроить локальный издатель](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span><span class="sxs-lookup"><span data-stu-id="a83ad-134">For instructions on configuring a client to use a local issuer, see [How to: Configure a Local Issuer](../../../wcf/feature-details/how-to-configure-a-local-issuer.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a83ad-135">См. также</span><span class="sxs-lookup"><span data-stu-id="a83ad-135">See also</span></span>

- <xref:System.ServiceModel.Configuration.IssuedTokenClientElement>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement>
- <xref:System.ServiceModel.Description.ClientCredentials>
- <xref:System.ServiceModel.Configuration.ClientCredentialsElement.IssuedToken%2A>
- <xref:System.ServiceModel.Description.ClientCredentials.IssuedToken%2A>
- <xref:System.ServiceModel.Security.IssuedTokenClientCredential>
- [<span data-ttu-id="a83ad-136">Поведение безопасности</span><span class="sxs-lookup"><span data-stu-id="a83ad-136">Security Behaviors</span></span>](../../../wcf/feature-details/security-behaviors-in-wcf.md)
- [<span data-ttu-id="a83ad-137">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="a83ad-137">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="a83ad-138">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="a83ad-138">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="a83ad-139">Обеспечение безопасности клиентов</span><span class="sxs-lookup"><span data-stu-id="a83ad-139">Securing Clients</span></span>](../../../wcf/securing-clients.md)
- [<span data-ttu-id="a83ad-140">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="a83ad-140">How to: Create a Federated Client</span></span>](../../../wcf/feature-details/how-to-create-a-federated-client.md)
- [<span data-ttu-id="a83ad-141">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="a83ad-141">How to: Configure a Local Issuer</span></span>](../../../wcf/feature-details/how-to-configure-a-local-issuer.md)
- [<span data-ttu-id="a83ad-142">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="a83ad-142">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
