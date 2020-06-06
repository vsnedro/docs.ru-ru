---
title: <security> из <msmqIntegrationBinding>
ms.date: 03/30/2017
ms.assetid: ae5c68a8-14a2-4c6e-b9e0-3e94e3e9135e
ms.openlocfilehash: 2268bf48a2b86c3b3b25db006e6f8f55ea33af73
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738680"
---
# <a name="security-of-msmqintegrationbinding"></a><span data-ttu-id="c1836-102">\<security> из \<msmqIntegrationBinding></span><span class="sxs-lookup"><span data-stu-id="c1836-102">\<security> of \<msmqIntegrationBinding></span></span>
<span data-ttu-id="c1836-103">Определяет параметры безопасности транспорта для канала интеграции очереди сообщений (MSMQ).</span><span class="sxs-lookup"><span data-stu-id="c1836-103">Defines the transport security settings for the Message Queuing (MSMQ) integration channel.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<msmqIntegrationBinding>**](msmqintegrationbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="c1836-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c1836-104">Syntax</span></span>  
  
```xml  
<msmqIntegrationBinding>
  <binding>
    <security mode="None/Transport">
      <transport msmqAuthenticationMode="None/Windows/Certificate"
                 msmqEncryptionAlgorithm="RC4Stream/AES"
                 msmqProtectionLevel="None/Sign/EncryptAndSign"
                 msmqSecureHashAlgorithm="MD5/SHA1/SHA256/SHA512" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="None/Windows/UserName/Certificate/CardSpace"
               defaultProtectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1836-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c1836-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c1836-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c1836-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1836-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c1836-107">Attributes</span></span>  
  
|<span data-ttu-id="c1836-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c1836-108">Attribute</span></span>|<span data-ttu-id="c1836-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c1836-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1836-110">mode</span><span class="sxs-lookup"><span data-stu-id="c1836-110">mode</span></span>|<span data-ttu-id="c1836-111">Задает тип системы безопасности, отвечающей за целостность, конфиденциальность и проверку подлинности при использовании канала интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="c1836-111">Specifies the type of security that controls integrity, confidentiality and authentication with the Message Queuing integration channel.</span></span> <span data-ttu-id="c1836-112">Допустимые значения.</span><span class="sxs-lookup"><span data-stu-id="c1836-112">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="c1836-113">-None: отключает безопасность.</span><span class="sxs-lookup"><span data-stu-id="c1836-113">-   None: This disables security.</span></span><br /><span data-ttu-id="c1836-114">-Transport: защита и проверка подлинности предоставляются транспортом.</span><span class="sxs-lookup"><span data-stu-id="c1836-114">-   Transport: Protection and authentication are offered by the transport.</span></span> <span data-ttu-id="c1836-115">Это значение связано с безопасностью сообщений между двумя диспетчерами очереди.</span><span class="sxs-lookup"><span data-stu-id="c1836-115">This applies to the message security between the two queue managers.</span></span> <span data-ttu-id="c1836-116">Между приложением и диспетчером очереди безопасность сообщений не обеспечивается.</span><span class="sxs-lookup"><span data-stu-id="c1836-116">There is no security offered between the application and queue manager.</span></span> <span data-ttu-id="c1836-117">Существующие Msmq-приложения функционально равноценны такому режиму безопасности.</span><span class="sxs-lookup"><span data-stu-id="c1836-117">Existing Msmq applications are functionally equivalent with this type of security mode.</span></span><br /><br /> <span data-ttu-id="c1836-118">Значение по умолчанию — `Transport`.</span><span class="sxs-lookup"><span data-stu-id="c1836-118">The default value is `Transport`.</span></span> <span data-ttu-id="c1836-119">Это атрибут типа <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="c1836-119">This attribute is of type <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurityMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1836-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c1836-120">Child Elements</span></span>  
  
|<span data-ttu-id="c1836-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="c1836-121">Element</span></span>|<span data-ttu-id="c1836-122">Описание</span><span class="sxs-lookup"><span data-stu-id="c1836-122">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-msmqintegrationbinding.md)|<span data-ttu-id="c1836-123">Определяет параметры безопасности для транспорта интеграции очереди сообщений.</span><span class="sxs-lookup"><span data-stu-id="c1836-123">Defines the security settings for the Message Queuing integration transport.</span></span> <span data-ttu-id="c1836-124">Это элемент типа <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c1836-124">This element is of type <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1836-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c1836-125">Parent Elements</span></span>  
  
|<span data-ttu-id="c1836-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="c1836-126">Element</span></span>|<span data-ttu-id="c1836-127">Описание</span><span class="sxs-lookup"><span data-stu-id="c1836-127">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="c1836-128">Элемент Binding объекта [\<msmqIntegrationBinding>](msmqintegrationbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c1836-128">The binding element of the [\<msmqIntegrationBinding>](msmqintegrationbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c1836-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c1836-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement.Security%2A>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationSecurity>
- [<span data-ttu-id="c1836-130">Очереди в WCF</span><span class="sxs-lookup"><span data-stu-id="c1836-130">Queues in WCF</span></span>](../../../wcf/feature-details/queues-in-wcf.md)
- [<span data-ttu-id="c1836-131">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c1836-131">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c1836-132">Привязки</span><span class="sxs-lookup"><span data-stu-id="c1836-132">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c1836-133">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="c1836-133">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c1836-134">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c1836-134">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [\<msmqIntegrationBinding>](msmqintegrationbinding.md)
