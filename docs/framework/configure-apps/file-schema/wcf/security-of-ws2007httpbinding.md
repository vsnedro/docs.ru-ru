---
title: <security> из <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736387"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="5981e-102">\<security> из \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="5981e-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="5981e-103">Представляет параметры безопасности, используемые с [\<ws2007HttpBinding>](ws2007httpbinding.md) элементом.</span><span class="sxs-lookup"><span data-stu-id="5981e-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="5981e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5981e-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5981e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5981e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5981e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5981e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5981e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5981e-107">Attributes</span></span>  
  
|<span data-ttu-id="5981e-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5981e-108">Attribute</span></span>|<span data-ttu-id="5981e-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="5981e-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="5981e-110">Используемых.</span><span class="sxs-lookup"><span data-stu-id="5981e-110">-   Optional.</span></span> <span data-ttu-id="5981e-111">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="5981e-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="5981e-112">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="5981e-112">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="5981e-113">Это атрибут типа <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5981e-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5981e-114">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="5981e-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="5981e-115">Значение</span><span class="sxs-lookup"><span data-stu-id="5981e-115">Value</span></span>|<span data-ttu-id="5981e-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5981e-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="5981e-117">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="5981e-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="5981e-118">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5981e-118">Security is provided using HTTPS.</span></span> <span data-ttu-id="5981e-119">Необходима настройка службы с помощью SSL-сертификатов.</span><span class="sxs-lookup"><span data-stu-id="5981e-119">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="5981e-120">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности службы выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="5981e-120">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="5981e-121">Проверка подлинности клиента контролируется с помощью `ClientCredentials` атрибута [\<transport>](transport-of-ws2007httpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="5981e-121">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="5981e-122">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="5981e-122">Security is provided using SOAP message security.</span></span> <span data-ttu-id="5981e-123">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="5981e-123">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="5981e-124">Этот режим предоставляет множество возможностей, например доступ к учетным данным службы для клиентов за пределами диапазона, выбор используемого набора алгоритмов и уровня защиты, применяемого к тексту сообщения посредством <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="5981e-124">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="5981e-125">Проверка подлинности клиента выполняется один раз для каждого сеанса, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5981e-125">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="5981e-126">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="5981e-126">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="5981e-127">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="5981e-127">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5981e-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5981e-128">Child Elements</span></span>  
  
|<span data-ttu-id="5981e-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="5981e-129">Element</span></span>|<span data-ttu-id="5981e-130">Описание</span><span class="sxs-lookup"><span data-stu-id="5981e-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="5981e-131">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="5981e-131">Defines the transport security settings.</span></span> <span data-ttu-id="5981e-132">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="5981e-132">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="5981e-133">Эти параметры применяются только в том случае, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="5981e-133">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="5981e-134">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="5981e-134">Defines the security settings for the message.</span></span> <span data-ttu-id="5981e-135">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="5981e-135">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="5981e-136">Эти параметры неприменимы, если режим имеет значение Transport.</span><span class="sxs-lookup"><span data-stu-id="5981e-136">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5981e-137">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5981e-137">Parent Elements</span></span>  
  
|<span data-ttu-id="5981e-138">Элемент</span><span class="sxs-lookup"><span data-stu-id="5981e-138">Element</span></span>|<span data-ttu-id="5981e-139">Описание</span><span class="sxs-lookup"><span data-stu-id="5981e-139">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="5981e-140">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="5981e-140">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5981e-141">Примечания</span><span class="sxs-lookup"><span data-stu-id="5981e-141">Remarks</span></span>  
 <span data-ttu-id="5981e-142">Этот элемент предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="5981e-142">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="5981e-143">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5981e-143">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5981e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="5981e-144">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="5981e-145">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5981e-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5981e-146">Привязки</span><span class="sxs-lookup"><span data-stu-id="5981e-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5981e-147">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="5981e-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5981e-148">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="5981e-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
