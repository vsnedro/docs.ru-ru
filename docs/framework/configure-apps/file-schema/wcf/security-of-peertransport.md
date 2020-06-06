---
title: <security> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: f73634ed-f896-4968-bf74-5e5ac52d3b6b
ms.openlocfilehash: 270ca844f586be256b6483653c868d1cc4396657
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399769"
---
# <a name="security-of-peertransport"></a><span data-ttu-id="cd567-102">\<security> из \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="cd567-102">\<security> of \<peerTransport></span></span>
<span data-ttu-id="cd567-103">Содержит параметры безопасности, связанные с одноранговым каналом, включая используемый тип проверки подлинности и механизм безопасности, применяемый при транспортировке сообщений.</span><span class="sxs-lookup"><span data-stu-id="cd567-103">Contains the security settings associated with a peer channel, including the type of authentication used and the security used for the message transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="cd567-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cd567-104">Syntax</span></span>  
  
```xml  
<security mode="None/Transport/Message/TransportWithMessageCredential">
  <transport clientCredentialType="None/Windows/UserName/Certificate/CardSpace" />
</security
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cd567-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="cd567-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cd567-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="cd567-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cd567-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="cd567-107">Attributes</span></span>  
  
|<span data-ttu-id="cd567-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="cd567-108">Attribute</span></span>|<span data-ttu-id="cd567-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="cd567-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="cd567-110">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="cd567-110">Specifies the type of security to be applied.</span></span> <span data-ttu-id="cd567-111">Значение по умолчанию - Message.</span><span class="sxs-lookup"><span data-stu-id="cd567-111">The default value is Message.</span></span> <span data-ttu-id="cd567-112">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="cd567-112">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="cd567-113">Атрибут mode</span><span class="sxs-lookup"><span data-stu-id="cd567-113">mode Attribute</span></span>  
  
|<span data-ttu-id="cd567-114">Значение</span><span class="sxs-lookup"><span data-stu-id="cd567-114">Value</span></span>|<span data-ttu-id="cd567-115">Описание</span><span class="sxs-lookup"><span data-stu-id="cd567-115">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="cd567-116">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="cd567-116">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="cd567-117">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="cd567-117">Security is provided using HTTPS.</span></span>|  
|`Message`|<span data-ttu-id="cd567-118">Механизм безопасности SOAP обеспечивает целостность, конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="cd567-118">SOAP security provides authentication, integrity and confidentiality.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="cd567-119">HTTPS обеспечивает конфиденциальность и проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="cd567-119">HTTPS provides authentication and confidentiality.</span></span> <span data-ttu-id="cd567-120">Сообщения SOAP предоставляют различные типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="cd567-120">SOAP messages provide rich credential types.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cd567-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="cd567-121">Child Elements</span></span>  
  
|<span data-ttu-id="cd567-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd567-122">Element</span></span>|<span data-ttu-id="cd567-123">Описание</span><span class="sxs-lookup"><span data-stu-id="cd567-123">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-peertransport.md)|<span data-ttu-id="cd567-124">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="cd567-124">Defines a peer transport for a custom binding.</span></span> <span data-ttu-id="cd567-125">Этот элемент имеет атрибут `clientCredentialType`, который задает учетные данные для использования при взаимодействии со службой.</span><span class="sxs-lookup"><span data-stu-id="cd567-125">This element has a `clientCredentialType` attribute that specifies the credentials to be used when interacting with a service.</span></span> <span data-ttu-id="cd567-126">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="cd567-126">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span><br /><br /> <span data-ttu-id="cd567-127">Это элемент типа <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="cd567-127">This element is of type <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cd567-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="cd567-128">Parent Elements</span></span>  
  
|<span data-ttu-id="cd567-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="cd567-129">Element</span></span>|<span data-ttu-id="cd567-130">Описание</span><span class="sxs-lookup"><span data-stu-id="cd567-130">Description</span></span>|  
|-------------|-----------------|  
|[\<peerTransport>](peertransport.md)|<span data-ttu-id="cd567-131">Определяет одноранговый транспорт для пользовательской привязки.</span><span class="sxs-lookup"><span data-stu-id="cd567-131">Defines a peer transport for a custom binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cd567-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cd567-132">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="cd567-133">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="cd567-133">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="cd567-134">Транспорты</span><span class="sxs-lookup"><span data-stu-id="cd567-134">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="cd567-135">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="cd567-135">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="cd567-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="cd567-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="cd567-137">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="cd567-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="cd567-138">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="cd567-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
