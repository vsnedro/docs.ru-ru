---
title: <security> из <netPeerBinding>
ms.date: 03/30/2017
ms.assetid: 1ef40d8c-f903-4426-9b08-da81462766d8
ms.openlocfilehash: 3d1ac85073c44f683fe0c054737c5ec7ed1cbf52
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738657"
---
# <a name="security-of-netpeerbinding"></a><span data-ttu-id="067d6-102">\<security> из \<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="067d6-102">\<security> of \<netPeerBinding></span></span>
<span data-ttu-id="067d6-103">Определяет параметры безопасности [\<netPeerTcpBinding>](netpeertcpbinding.md) , включая тип используемой проверки подлинности и безопасность, используемую для транспорта сообщений.</span><span class="sxs-lookup"><span data-stu-id="067d6-103">Defines the security settings of the [\<netPeerTcpBinding>](netpeertcpbinding.md), including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="067d6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="067d6-104">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding>
    <security mode="Message/None/Transport//TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="067d6-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="067d6-105">Attributes and Elements</span></span>  
 <span data-ttu-id="067d6-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="067d6-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="067d6-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="067d6-107">Attributes</span></span>  
  
|<span data-ttu-id="067d6-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="067d6-108">Attribute</span></span>|<span data-ttu-id="067d6-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="067d6-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="067d6-110">mode</span><span class="sxs-lookup"><span data-stu-id="067d6-110">mode</span></span>|<span data-ttu-id="067d6-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="067d6-111">Optional.</span></span> <span data-ttu-id="067d6-112">Указывает тип безопасности, используемый одноранговыми узлами, настроенными с использованием этой привязки.</span><span class="sxs-lookup"><span data-stu-id="067d6-112">Specifies the type of security used by peers configured with this binding.</span></span> <span data-ttu-id="067d6-113">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="067d6-113">The default value is `Message`.</span></span> <span data-ttu-id="067d6-114">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="067d6-114">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="067d6-115">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="067d6-115">mode Attribute</span></span>  
  
|<span data-ttu-id="067d6-116">Значение</span><span class="sxs-lookup"><span data-stu-id="067d6-116">Value</span></span>|<span data-ttu-id="067d6-117">Описание</span><span class="sxs-lookup"><span data-stu-id="067d6-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="067d6-118">Сообщение</span><span class="sxs-lookup"><span data-stu-id="067d6-118">Message</span></span>|<span data-ttu-id="067d6-119">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="067d6-119">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|<span data-ttu-id="067d6-120">Нет</span><span class="sxs-lookup"><span data-stu-id="067d6-120">None</span></span>|<span data-ttu-id="067d6-121">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="067d6-121">Security is disabled.</span></span>|  
|<span data-ttu-id="067d6-122">Транспорт</span><span class="sxs-lookup"><span data-stu-id="067d6-122">Transport</span></span>|<span data-ttu-id="067d6-123">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="067d6-123">Security is provided using HTTPS.</span></span>|  
|<span data-ttu-id="067d6-124">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="067d6-124">TransportWithMessageCredential</span></span>|<span data-ttu-id="067d6-125">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="067d6-125">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="067d6-126">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="067d6-126">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="067d6-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="067d6-127">Child Elements</span></span>  
  
|<span data-ttu-id="067d6-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="067d6-128">Element</span></span>|<span data-ttu-id="067d6-129">Описание</span><span class="sxs-lookup"><span data-stu-id="067d6-129">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-netpeertcpbinding.md)|<span data-ttu-id="067d6-130">Определяет тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="067d6-130">Defines the transport type for secured messages sent by peers configured with this binding.</span></span> <span data-ttu-id="067d6-131">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="067d6-131">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="067d6-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="067d6-132">Parent Elements</span></span>  
  
|<span data-ttu-id="067d6-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="067d6-133">Element</span></span>|<span data-ttu-id="067d6-134">Описание</span><span class="sxs-lookup"><span data-stu-id="067d6-134">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="067d6-135">Определяет все возможности привязки [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="067d6-135">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="067d6-136">Примечания</span><span class="sxs-lookup"><span data-stu-id="067d6-136">Remarks</span></span>  
 <span data-ttu-id="067d6-137">Безопасность может определяться как на уровне сообщений, так и на уровне транспорта.</span><span class="sxs-lookup"><span data-stu-id="067d6-137">Security can be either message- or transport-specific.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="067d6-138">См. также</span><span class="sxs-lookup"><span data-stu-id="067d6-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.NetPeerTcpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Security%2A>
- <xref:System.ServiceModel.PeerSecuritySettings>
- [<span data-ttu-id="067d6-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="067d6-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="067d6-140">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="067d6-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="067d6-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="067d6-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="067d6-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="067d6-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="067d6-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="067d6-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
