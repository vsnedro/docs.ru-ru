---
title: <security> из <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: 48b49bf69f791f90ed5b2eea8e6d412438cd9519
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169847"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="e5cf5-102">\<security> из \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="e5cf5-102">\<security> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="e5cf5-103">Представляет параметры безопасности, используемые с [\<ws2007HttpBinding>](ws2007httpbinding.md) элементом.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="e5cf5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5cf5-104">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e5cf5-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e5cf5-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e5cf5-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e5cf5-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e5cf5-107">Attributes</span></span>  
  
|<span data-ttu-id="e5cf5-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e5cf5-108">Attribute</span></span>|<span data-ttu-id="e5cf5-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e5cf5-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="e5cf5-110">Используемых.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-110">-   Optional.</span></span> <span data-ttu-id="e5cf5-111">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="e5cf5-112">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-112">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="e5cf5-113">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e5cf5-114">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="e5cf5-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="e5cf5-115">Значение</span><span class="sxs-lookup"><span data-stu-id="e5cf5-115">Value</span></span>|<span data-ttu-id="e5cf5-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e5cf5-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e5cf5-117">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="e5cf5-118">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-118">Security is provided using HTTPS.</span></span> <span data-ttu-id="e5cf5-119">Необходима настройка службы с помощью SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-119">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="e5cf5-120">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-120">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e5cf5-121">Проверка подлинности клиента контролируется с помощью `ClientCredentials` атрибута [\<transport>](transport-of-ws2007httpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-121">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="e5cf5-122">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-122">Security is provided using SOAP message security.</span></span> <span data-ttu-id="e5cf5-123">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-123">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="e5cf5-124">Этот режим предоставляет множество возможностей, например доступ к учетным данным службы для клиентов за пределами диапазона, выбор используемого набора алгоритмов и уровня защиты, применяемого к тексту сообщения посредством <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-124">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="e5cf5-125">Проверка подлинности клиента выполняется один раз для каждого сеанса, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-125">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="e5cf5-126">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-126">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="e5cf5-127">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-127">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e5cf5-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e5cf5-128">Child Elements</span></span>  
  
|<span data-ttu-id="e5cf5-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5cf5-129">Element</span></span>|<span data-ttu-id="e5cf5-130">Описание</span><span class="sxs-lookup"><span data-stu-id="e5cf5-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="e5cf5-131">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-131">Defines the transport security settings.</span></span> <span data-ttu-id="e5cf5-132">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-132">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="e5cf5-133">Эти параметры применяются только в том случае, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-133">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="e5cf5-134">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-134">Defines the security settings for the message.</span></span> <span data-ttu-id="e5cf5-135">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-135">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="e5cf5-136">Эти параметры неприменимы, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-136">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e5cf5-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e5cf5-137">Parent Elements</span></span>  
  
|<span data-ttu-id="e5cf5-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="e5cf5-138">Element</span></span>|<span data-ttu-id="e5cf5-139">Описание</span><span class="sxs-lookup"><span data-stu-id="e5cf5-139">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="e5cf5-140">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-140">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e5cf5-141">Remarks</span><span class="sxs-lookup"><span data-stu-id="e5cf5-141">Remarks</span></span>  

 <span data-ttu-id="e5cf5-142">Этот элемент предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-142">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="e5cf5-143">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e5cf5-143">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5cf5-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5cf5-144">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="e5cf5-145">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e5cf5-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e5cf5-146">Привязки</span><span class="sxs-lookup"><span data-stu-id="e5cf5-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e5cf5-147">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="e5cf5-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e5cf5-148">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="e5cf5-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
