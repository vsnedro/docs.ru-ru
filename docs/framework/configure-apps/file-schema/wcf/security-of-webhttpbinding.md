---
title: <security> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738635"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="3cffd-102">\<security> из \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="3cffd-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="3cffd-103">Указывает требования к безопасности для конечной точки, настроенной с помощью [\<webHttpBinding>](webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3cffd-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="3cffd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cffd-104">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3cffd-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3cffd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3cffd-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3cffd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3cffd-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3cffd-107">Attributes</span></span>  
  
|<span data-ttu-id="3cffd-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="3cffd-108">Attribute</span></span>|<span data-ttu-id="3cffd-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="3cffd-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3cffd-110">mode</span><span class="sxs-lookup"><span data-stu-id="3cffd-110">mode</span></span>|<span data-ttu-id="3cffd-111">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="3cffd-111">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="3cffd-112">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="3cffd-112">The default is `None`.</span></span> <span data-ttu-id="3cffd-113">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3cffd-113">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3cffd-114">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="3cffd-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="3cffd-115">Значение</span><span class="sxs-lookup"><span data-stu-id="3cffd-115">Value</span></span>|<span data-ttu-id="3cffd-116">Описание</span><span class="sxs-lookup"><span data-stu-id="3cffd-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3cffd-117">None</span><span class="sxs-lookup"><span data-stu-id="3cffd-117">None</span></span>|<span data-ttu-id="3cffd-118">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="3cffd-118">Security is disabled.</span></span>|  
|<span data-ttu-id="3cffd-119">Транспорт</span><span class="sxs-lookup"><span data-stu-id="3cffd-119">Transport</span></span>|<span data-ttu-id="3cffd-120">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3cffd-120">Security is provided using HTTPS.</span></span> <span data-ttu-id="3cffd-121">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="3cffd-121">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="3cffd-122">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="3cffd-122">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="3cffd-123">Проверка подлинности клиента контролируется с помощью `ClientCredentialType` атрибута [\<transport>](transport-of-webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="3cffd-123">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="3cffd-124">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="3cffd-124">TransportCredentialOnly</span></span>|<span data-ttu-id="3cffd-125">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="3cffd-125">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="3cffd-126">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="3cffd-126">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="3cffd-127">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="3cffd-127">This mode should be used with caution.</span></span> <span data-ttu-id="3cffd-128">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="3cffd-128">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3cffd-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3cffd-129">Child Elements</span></span>  
  
|<span data-ttu-id="3cffd-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cffd-130">Element</span></span>|<span data-ttu-id="3cffd-131">Описание</span><span class="sxs-lookup"><span data-stu-id="3cffd-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="3cffd-132">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="3cffd-132">Defines the transport security settings.</span></span> <span data-ttu-id="3cffd-133">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="3cffd-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3cffd-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3cffd-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3cffd-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="3cffd-135">Element</span></span>|<span data-ttu-id="3cffd-136">Описание</span><span class="sxs-lookup"><span data-stu-id="3cffd-136">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="3cffd-137">Элемент Binding, который используется для настройки конечных точек для веб-служб Windows Communication Foundation (WCF), которые реагируют на запросы HTTP, а не сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="3cffd-137">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3cffd-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3cffd-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="3cffd-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3cffd-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="3cffd-140">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="3cffd-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="3cffd-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="3cffd-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="3cffd-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="3cffd-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="3cffd-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="3cffd-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="3cffd-144">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="3cffd-144">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
