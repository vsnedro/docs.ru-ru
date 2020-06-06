---
title: <security> из <netMsmqBinding>
ms.date: 03/30/2017
ms.assetid: 001d11a9-7439-498c-b09d-fca20eaf8cd3
ms.openlocfilehash: 7877fd59aff581eee5b62a1ca224dbf51c956069
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738678"
---
# <a name="security-of-netmsmqbinding"></a><span data-ttu-id="6221b-102">\<security> из \<netMsmqBinding></span><span class="sxs-lookup"><span data-stu-id="6221b-102">\<security> of \<netMsmqBinding></span></span>
<span data-ttu-id="6221b-103">Определяет параметры безопасности для привязки MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6221b-103">Defines the security settings for a MSMQ binding.</span></span> <span data-ttu-id="6221b-104">Он указывает, включена ли поддержка транспорта или безопасности SOAP и, если поддержка включена, указывает используемые уровни защиты и режим проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6221b-104">It specifies whether transport or SOAP security is enabled and, if so, what authentication mode and protection levels are in use.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netMsmqBinding>**](netmsmqbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="6221b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6221b-105">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/Both">
  <transport msmqAuthenticationMode="None/WindowsDomain/Certificate"
             msmqEncryptionAlgorithm="RC4Stream/AES"
             msmqProtectionLevel="None/Sign/EncryptAndSign"
             msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
    <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
             clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6221b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6221b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="6221b-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6221b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6221b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6221b-108">Attributes</span></span>  
  
|<span data-ttu-id="6221b-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6221b-109">Attribute</span></span>|<span data-ttu-id="6221b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="6221b-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6221b-111">mode</span><span class="sxs-lookup"><span data-stu-id="6221b-111">mode</span></span>|<span data-ttu-id="6221b-112">Задает тип безопасности, который контролирует целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="6221b-112">Specifies the type of security that controls integrity, confidentiality and authentication.</span></span> <span data-ttu-id="6221b-113">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="6221b-113">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="6221b-114">-None: отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="6221b-114">-   None: This disables security.</span></span><br /><span data-ttu-id="6221b-115">-Transport: защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="6221b-115">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="6221b-116">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="6221b-116">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="6221b-117">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="6221b-117">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="6221b-118">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="6221b-118">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><span data-ttu-id="6221b-119">-Message: определяет безопасность конечного приложения.</span><span class="sxs-lookup"><span data-stu-id="6221b-119">-   Message: Specifies end-end application security.</span></span> <span data-ttu-id="6221b-120">Безопасность на транспортном уровне не предоставляется.</span><span class="sxs-lookup"><span data-stu-id="6221b-120">There is no security offered at the transport layer.</span></span> <span data-ttu-id="6221b-121">Такие параметры аналогичны параметрам безопасности, предоставляемой другими стандартными привязками.</span><span class="sxs-lookup"><span data-stu-id="6221b-121">This is similar to the security offered by other standard bindings.</span></span><br /><span data-ttu-id="6221b-122">Оба: обеспечивают безопасность на уровне транспорта и сообщений протокола SOAP.</span><span class="sxs-lookup"><span data-stu-id="6221b-122">-   Both: Offers security at both the transport and SOAP messaging layer.</span></span> <span data-ttu-id="6221b-123">На обоих уровнях требуются одни и те же учетные данные.</span><span class="sxs-lookup"><span data-stu-id="6221b-123">The same credential is required at both the levels.</span></span><br /><br /> <span data-ttu-id="6221b-124">Значение по умолчанию - Transport.</span><span class="sxs-lookup"><span data-stu-id="6221b-124">The default value is Transport.</span></span> <span data-ttu-id="6221b-125">Это атрибут типа <xref:System.ServiceModel.NetMsmqSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="6221b-125">This attribute is of type <xref:System.ServiceModel.NetMsmqSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6221b-126">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6221b-126">Child Elements</span></span>  
  
|<span data-ttu-id="6221b-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="6221b-127">Element</span></span>|<span data-ttu-id="6221b-128">Описание</span><span class="sxs-lookup"><span data-stu-id="6221b-128">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-netmsmqbinding.md)|<span data-ttu-id="6221b-129">Определяет параметры безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="6221b-129">Defines the SOAP message security settings.</span></span> <span data-ttu-id="6221b-130">Это элемент типа <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span><span class="sxs-lookup"><span data-stu-id="6221b-130">This element is of type <xref:System.ServiceModel.Configuration.MessageSecurityOverMsmqElement>.</span></span>|  
|[\<transport>](transport-of-netmsmqbinding.md)|<span data-ttu-id="6221b-131">Определяет параметры безопасности для транспорта MSMQ.</span><span class="sxs-lookup"><span data-stu-id="6221b-131">Defines the security settings for the MSMQ transport.</span></span> <span data-ttu-id="6221b-132">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="6221b-132">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6221b-133">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6221b-133">Parent Elements</span></span>  
  
|<span data-ttu-id="6221b-134">Элемент</span><span class="sxs-lookup"><span data-stu-id="6221b-134">Element</span></span>|<span data-ttu-id="6221b-135">Описание</span><span class="sxs-lookup"><span data-stu-id="6221b-135">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6221b-136">binding</span><span class="sxs-lookup"><span data-stu-id="6221b-136">binding</span></span>|<span data-ttu-id="6221b-137">Элемент binding элемента[\<netMsmqBinding>](netmsmqbinding.md)</span><span class="sxs-lookup"><span data-stu-id="6221b-137">The binding element of the [\<netMsmqBinding>](netmsmqbinding.md)</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6221b-138">См. также</span><span class="sxs-lookup"><span data-stu-id="6221b-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.NetMsmqSecurityElement>
- <xref:System.ServiceModel.NetMsmqBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetMsmqBindingElement.Security%2A>
- <xref:System.ServiceModel.NetMsmqSecurity>
- [<span data-ttu-id="6221b-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6221b-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="6221b-140">Привязки</span><span class="sxs-lookup"><span data-stu-id="6221b-140">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6221b-141">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="6221b-141">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="6221b-142">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="6221b-142">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="6221b-143">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="6221b-143">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
