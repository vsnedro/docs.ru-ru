---
title: <security> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 60b863a0a2a846a60dde2e4b323a305b5096b1cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169899"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="ba40d-102">\<security> из \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="ba40d-102">\<security> of \<webHttpBinding></span></span>

<span data-ttu-id="ba40d-103">Указывает требования к безопасности для конечной точки, настроенной с помощью [\<webHttpBinding>](webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ba40d-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="ba40d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ba40d-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba40d-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ba40d-105">Attributes and Elements</span></span>  

 <span data-ttu-id="ba40d-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ba40d-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba40d-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ba40d-107">Attributes</span></span>  
  
|<span data-ttu-id="ba40d-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ba40d-108">Attribute</span></span>|<span data-ttu-id="ba40d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="ba40d-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ba40d-110">mode</span><span class="sxs-lookup"><span data-stu-id="ba40d-110">mode</span></span>|<span data-ttu-id="ba40d-111">Указывает, использует ли конечная точка безопасность на уровне транспорта, или же режим обеспечения безопасности не используется.</span><span class="sxs-lookup"><span data-stu-id="ba40d-111">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="ba40d-112">Значение по умолчанию — `None`.</span><span class="sxs-lookup"><span data-stu-id="ba40d-112">The default is `None`.</span></span> <span data-ttu-id="ba40d-113">Это атрибут типа <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="ba40d-113">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="ba40d-114">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="ba40d-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="ba40d-115">Значение</span><span class="sxs-lookup"><span data-stu-id="ba40d-115">Value</span></span>|<span data-ttu-id="ba40d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="ba40d-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ba40d-117">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="ba40d-117">None</span></span>|<span data-ttu-id="ba40d-118">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="ba40d-118">Security is disabled.</span></span>|  
|<span data-ttu-id="ba40d-119">Транспорт</span><span class="sxs-lookup"><span data-stu-id="ba40d-119">Transport</span></span>|<span data-ttu-id="ba40d-120">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="ba40d-120">Security is provided using HTTPS.</span></span> <span data-ttu-id="ba40d-121">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="ba40d-121">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="ba40d-122">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="ba40d-122">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="ba40d-123">Проверка подлинности клиента контролируется с помощью `ClientCredentialType` атрибута [\<transport>](transport-of-webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="ba40d-123">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="ba40d-124">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="ba40d-124">TransportCredentialOnly</span></span>|<span data-ttu-id="ba40d-125">Данный режим не обеспечивает целостности и конфиденциальности сообщений.</span><span class="sxs-lookup"><span data-stu-id="ba40d-125">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="ba40d-126">Он обеспечивает проверку подлинности клиента на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="ba40d-126">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="ba40d-127">Этот режим следует использовать с осторожностью.</span><span class="sxs-lookup"><span data-stu-id="ba40d-127">This mode should be used with caution.</span></span> <span data-ttu-id="ba40d-128">Он должен использоваться в средах, где безопасность транспорта предоставляется другими средствами (например, IPSec), а инфраструктура WCF предоставляет только проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="ba40d-128">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ba40d-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ba40d-129">Child Elements</span></span>  
  
|<span data-ttu-id="ba40d-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba40d-130">Element</span></span>|<span data-ttu-id="ba40d-131">Описание</span><span class="sxs-lookup"><span data-stu-id="ba40d-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="ba40d-132">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="ba40d-132">Defines the transport security settings.</span></span> <span data-ttu-id="ba40d-133">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="ba40d-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba40d-134">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ba40d-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ba40d-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="ba40d-135">Element</span></span>|<span data-ttu-id="ba40d-136">Описание</span><span class="sxs-lookup"><span data-stu-id="ba40d-136">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="ba40d-137">Элемент Binding, который используется для настройки конечных точек для веб-служб Windows Communication Foundation (WCF), которые реагируют на запросы HTTP, а не сообщения SOAP.</span><span class="sxs-lookup"><span data-stu-id="ba40d-137">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ba40d-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ba40d-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="ba40d-139">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ba40d-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="ba40d-140">Выбор типа учетных данных</span><span class="sxs-lookup"><span data-stu-id="ba40d-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="ba40d-141">Привязки</span><span class="sxs-lookup"><span data-stu-id="ba40d-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="ba40d-142">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="ba40d-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="ba40d-143">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="ba40d-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="ba40d-144">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="ba40d-144">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
