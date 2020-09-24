---
title: <transport> из <peerTransport>
ms.date: 03/30/2017
ms.assetid: d7116240-845c-4b6f-b203-262de6b597ef
ms.openlocfilehash: 7328d67c4649010dce3e1c866238d1e0067e4990
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91157074"
---
# <a name="transport-of-peertransport"></a><span data-ttu-id="e173f-102">\<transport> из \<peerTransport></span><span class="sxs-lookup"><span data-stu-id="e173f-102">\<transport> of \<peerTransport></span></span>

<span data-ttu-id="e173f-103">Задает тип транспорта для безопасных сообщений, отправленных одноранговыми узлами, настроенными с помощью этой привязки.</span><span class="sxs-lookup"><span data-stu-id="e173f-103">Specifies the transport type for secured messages sent by peers configured with this binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peerTransport>**](peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-peertransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="e173f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e173f-104">Syntax</span></span>  
  
```xml  
<security>
  <transport credentialType="Certificate/Password" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e173f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e173f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e173f-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e173f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e173f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e173f-107">Attributes</span></span>  
  
|<span data-ttu-id="e173f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e173f-108">Attribute</span></span>|<span data-ttu-id="e173f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e173f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e173f-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="e173f-110">credentialType</span></span>|<span data-ttu-id="e173f-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="e173f-111">Optional.</span></span> <span data-ttu-id="e173f-112">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="e173f-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="e173f-113">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e173f-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="e173f-114">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="e173f-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="e173f-115">Значение</span><span class="sxs-lookup"><span data-stu-id="e173f-115">Value</span></span>|<span data-ttu-id="e173f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e173f-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e173f-117">Сертификат</span><span class="sxs-lookup"><span data-stu-id="e173f-117">Certificate</span></span>|<span data-ttu-id="e173f-118">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="e173f-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="e173f-119">Пароль</span><span class="sxs-lookup"><span data-stu-id="e173f-119">Password</span></span>|<span data-ttu-id="e173f-120">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="e173f-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e173f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e173f-121">Child Elements</span></span>  

 <span data-ttu-id="e173f-122">Нет</span><span class="sxs-lookup"><span data-stu-id="e173f-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e173f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e173f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="e173f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="e173f-124">Element</span></span>|<span data-ttu-id="e173f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="e173f-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-peertransport.md)|<span data-ttu-id="e173f-126">Определяет параметры безопасности для однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="e173f-126">Defines the security settings for a peer transport.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e173f-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="e173f-127">Remarks</span></span>  

 <span data-ttu-id="e173f-128">Этот элемент задается только в том случае, если атрибут mode [\<security>](security-of-peertransport.md) имеет значение `Transport` или `TransportWithMessageCredential` .</span><span class="sxs-lookup"><span data-stu-id="e173f-128">This element is set only if the mode attribute of [\<security>](security-of-peertransport.md) is set to `Transport` or `TransportWithMessageCredential`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e173f-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e173f-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e173f-130">Безопасность транспорта</span><span class="sxs-lookup"><span data-stu-id="e173f-130">Transport Security</span></span>](../../../wcf/feature-details/transport-security.md)
- [<span data-ttu-id="e173f-131">Транспорты</span><span class="sxs-lookup"><span data-stu-id="e173f-131">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="e173f-132">Выбор транспортов</span><span class="sxs-lookup"><span data-stu-id="e173f-132">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="e173f-133">Привязки</span><span class="sxs-lookup"><span data-stu-id="e173f-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e173f-134">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="e173f-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e173f-135">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="e173f-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
