---
title: <security> из <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: 4969c041678bbf3490975bc0ec53507b6cf762bb
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738607"
---
# <a name="security-of-wsdualhttpbinding"></a><span data-ttu-id="5337b-102">\<security> из \<wsDualHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5337b-102">\<security> of \<wsDualHttpBinding></span></span>
<span data-ttu-id="5337b-103">Определяет возможности безопасности для [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5337b-103">Defines the security capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsDualHttpBinding>**](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="5337b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5337b-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5337b-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5337b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5337b-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5337b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5337b-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5337b-107">Attributes</span></span>  
  
|<span data-ttu-id="5337b-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5337b-108">Attribute</span></span>|<span data-ttu-id="5337b-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="5337b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5337b-110">mode</span><span class="sxs-lookup"><span data-stu-id="5337b-110">mode</span></span>|<span data-ttu-id="5337b-111">Используемых.</span><span class="sxs-lookup"><span data-stu-id="5337b-111">-   Optional.</span></span> <span data-ttu-id="5337b-112">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="5337b-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="5337b-113">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="5337b-113">The default value is `Message`.</span></span> <span data-ttu-id="5337b-114">Это атрибут типа <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5337b-114">This attribute is of type <xref:System.ServiceModel.WSDualHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5337b-115">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="5337b-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="5337b-116">Значение</span><span class="sxs-lookup"><span data-stu-id="5337b-116">Value</span></span>|<span data-ttu-id="5337b-117">Описание</span><span class="sxs-lookup"><span data-stu-id="5337b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5337b-118">None</span><span class="sxs-lookup"><span data-stu-id="5337b-118">None</span></span>|<span data-ttu-id="5337b-119">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="5337b-119">Security is disabled.</span></span>|  
|<span data-ttu-id="5337b-120">Сообщение</span><span class="sxs-lookup"><span data-stu-id="5337b-120">Message</span></span>|<span data-ttu-id="5337b-121">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="5337b-121">Security is provided using SOAP message security.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5337b-122">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5337b-122">Child Elements</span></span>  
  
|<span data-ttu-id="5337b-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="5337b-123">Element</span></span>|<span data-ttu-id="5337b-124">Описание</span><span class="sxs-lookup"><span data-stu-id="5337b-124">Description</span></span>|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|<span data-ttu-id="5337b-125">Определяет параметры безопасности уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="5337b-125">Defines the settings for the message-level security.</span></span> <span data-ttu-id="5337b-126">Это элемент типа <xref:System.ServiceModel.MessageSecurityOverHttp>.</span><span class="sxs-lookup"><span data-stu-id="5337b-126">This element is of type <xref:System.ServiceModel.MessageSecurityOverHttp>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5337b-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5337b-127">Parent Elements</span></span>  
  
|<span data-ttu-id="5337b-128">Элемент</span><span class="sxs-lookup"><span data-stu-id="5337b-128">Element</span></span>|<span data-ttu-id="5337b-129">Описание</span><span class="sxs-lookup"><span data-stu-id="5337b-129">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="5337b-130">Определяет все возможности привязки [\<wsDualHttpBinding>](wsdualhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5337b-130">Defines all binding capabilities of the [\<wsDualHttpBinding>](wsdualhttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5337b-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="5337b-131">Remarks</span></span>  
 <span data-ttu-id="5337b-132">Двойная привязка предоставляет службе IP-адрес клиента.</span><span class="sxs-lookup"><span data-stu-id="5337b-132">A dual binding exposes the IP address of the client to the service.</span></span> <span data-ttu-id="5337b-133">Клиенту следует использовать механизм безопасности, чтобы гарантировать, что подключение выполняется только к доверенным службам.</span><span class="sxs-lookup"><span data-stu-id="5337b-133">The client should use security to ensure that it only connects to services it trusts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5337b-134">См. также</span><span class="sxs-lookup"><span data-stu-id="5337b-134">See also</span></span>

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="5337b-135">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5337b-135">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5337b-136">Привязки</span><span class="sxs-lookup"><span data-stu-id="5337b-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5337b-137">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="5337b-137">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5337b-138">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5337b-138">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
