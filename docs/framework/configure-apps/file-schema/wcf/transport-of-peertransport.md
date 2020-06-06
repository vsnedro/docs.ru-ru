---
title: <transport> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 3b2c7716727f58abb81bf4d58b13189ac170cf7c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70399292"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="d601e-102">\<transport> из \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="d601e-102">\<transport> of \<peerTransport></span></span>
<span data-ttu-id="d601e-103">Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="d601e-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="d601e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d601e-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d601e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="d601e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="d601e-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="d601e-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d601e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="d601e-107">Attributes</span></span>  
  
|<span data-ttu-id="d601e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="d601e-108">Attribute</span></span>|<span data-ttu-id="d601e-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="d601e-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d601e-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="d601e-110">credentialType</span></span>|<span data-ttu-id="d601e-111">Необязательный параметр.</span><span class="sxs-lookup"><span data-stu-id="d601e-111">Optional.</span></span> <span data-ttu-id="d601e-112">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="d601e-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="d601e-113">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="d601e-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="d601e-114">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="d601e-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="d601e-115">Значение</span><span class="sxs-lookup"><span data-stu-id="d601e-115">Value</span></span>|<span data-ttu-id="d601e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="d601e-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d601e-117">Сертификат</span><span class="sxs-lookup"><span data-stu-id="d601e-117">Certificate</span></span>|<span data-ttu-id="d601e-118">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="d601e-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="d601e-119">Пароль</span><span class="sxs-lookup"><span data-stu-id="d601e-119">Password</span></span>|<span data-ttu-id="d601e-120">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="d601e-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d601e-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="d601e-121">Child Elements</span></span>  
 <span data-ttu-id="d601e-122">Нет</span><span class="sxs-lookup"><span data-stu-id="d601e-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d601e-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="d601e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="d601e-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="d601e-124">Element</span></span>|<span data-ttu-id="d601e-125">Описание</span><span class="sxs-lookup"><span data-stu-id="d601e-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="d601e-126">Определяет параметры безопасности для однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="d601e-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d601e-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="d601e-127">Remarks</span></span>  
 <span data-ttu-id="d601e-128">Этот элемент задается только в том случае, если атрибут mode [\<security>](security-of-peertransport.md) имеет значение `Transport` или `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="d601e-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d601e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="d601e-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="d601e-130">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="d601e-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="d601e-131">Транспорты</span><span class="sxs-lookup"><span data-stu-id="d601e-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="d601e-132">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="d601e-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="d601e-133">Привязки</span><span class="sxs-lookup"><span data-stu-id="d601e-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d601e-134">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="d601e-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="d601e-135">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="d601e-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
