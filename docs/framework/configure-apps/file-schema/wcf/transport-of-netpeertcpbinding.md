---
title: <transport> из <netPeerTcpBinding>
ms.date: 03/30/2017
ms.assetid: c44d86d2-1160-44d7-9c7a-297b12eccc7f
ms.openlocfilehash: 5df47b1bfc149b524fc9b90eacffa832817f653c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172870"
---
# <a name="transport-of-netpeertcpbinding"></a><span data-ttu-id="3128f-102">\<transport> из \<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="3128f-102">\<transport> of \<netPeerTcpBinding></span></span>

<span data-ttu-id="3128f-103">Задает параметры безопасности на транспортном уровне при использовании [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3128f-103">Specifies settings for transport level security when using the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netpeerbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="3128f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3128f-104">Syntax</span></span>  
  
```xml  
<netPeerTcpBinding>
  <binding>
    <security>
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerTcpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3128f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3128f-105">Attributes and Elements</span></span>  

 <span data-ttu-id="3128f-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3128f-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3128f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3128f-107">Attributes</span></span>  
  
|<span data-ttu-id="3128f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3128f-108">Attribute</span></span>|<span data-ttu-id="3128f-109">Описание</span><span class="sxs-lookup"><span data-stu-id="3128f-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3128f-110">credentialType</span><span class="sxs-lookup"><span data-stu-id="3128f-110">credentialType</span></span>|<span data-ttu-id="3128f-111">Необязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3128f-111">Optional.</span></span> <span data-ttu-id="3128f-112">Задает тип учетных данных, используемых для проверки сообщений, отправляемых с помощью однорангового транспорта.</span><span class="sxs-lookup"><span data-stu-id="3128f-112">Specifies the type of credentials used to verify messages sent with the peer transport.</span></span> <span data-ttu-id="3128f-113">Это атрибут типа <xref:System.ServiceModel.PeerTransportCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="3128f-113">This attribute is of type <xref:System.ServiceModel.PeerTransportCredentialType>.</span></span>|  
  
## <a name="credentialtype-attribute"></a><span data-ttu-id="3128f-114">Атрибут credentialType</span><span class="sxs-lookup"><span data-stu-id="3128f-114">credentialType Attribute</span></span>  
  
|<span data-ttu-id="3128f-115">Значение</span><span class="sxs-lookup"><span data-stu-id="3128f-115">Value</span></span>|<span data-ttu-id="3128f-116">Описание</span><span class="sxs-lookup"><span data-stu-id="3128f-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3128f-117">Сертификат</span><span class="sxs-lookup"><span data-stu-id="3128f-117">Certificate</span></span>|<span data-ttu-id="3128f-118">Для проверки подлинности однорангового транспорта канала необходим сертификат X.509.</span><span class="sxs-lookup"><span data-stu-id="3128f-118">Authentication of the peer channel transport requires an X509 certificate.</span></span>|  
|<span data-ttu-id="3128f-119">Пароль</span><span class="sxs-lookup"><span data-stu-id="3128f-119">Password</span></span>|<span data-ttu-id="3128f-120">Для проверки подлинности однорангового транспорта канала необходим правильный пароль.</span><span class="sxs-lookup"><span data-stu-id="3128f-120">Authentication of the peer channel transport requires a correct password.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3128f-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3128f-121">Child Elements</span></span>  

 <span data-ttu-id="3128f-122">Нет</span><span class="sxs-lookup"><span data-stu-id="3128f-122">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3128f-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3128f-123">Parent Elements</span></span>  
  
|<span data-ttu-id="3128f-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="3128f-124">Element</span></span>|<span data-ttu-id="3128f-125">Описание</span><span class="sxs-lookup"><span data-stu-id="3128f-125">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="3128f-126">Определяет параметры безопасности для [\<netPeerTcpBinding>](netpeertcpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3128f-126">Defines the security settings for the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3128f-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3128f-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportSecurityElement>
- <xref:System.ServiceModel.PeerSecuritySettings.Transport%2A>
- <xref:System.ServiceModel.Configuration.PeerSecurityElement.Transport%2A>
- <xref:System.ServiceModel.PeerTransportSecuritySettings>
- [<span data-ttu-id="3128f-128">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3128f-128">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3128f-129">Привязки</span><span class="sxs-lookup"><span data-stu-id="3128f-129">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3128f-130">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="3128f-130">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3128f-131">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3128f-131">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
