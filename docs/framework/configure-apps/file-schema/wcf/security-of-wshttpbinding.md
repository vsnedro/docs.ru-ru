---
title: <security> из <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738582"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="c2eba-102">\<security> из \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="c2eba-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="c2eba-103">Представляет возможности безопасности [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c2eba-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="c2eba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2eba-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c2eba-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="c2eba-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c2eba-106">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="c2eba-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c2eba-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="c2eba-107">Attributes</span></span>  
  
|<span data-ttu-id="c2eba-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="c2eba-108">Attribute</span></span>|<span data-ttu-id="c2eba-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="c2eba-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c2eba-110">mode</span><span class="sxs-lookup"><span data-stu-id="c2eba-110">mode</span></span>|<span data-ttu-id="c2eba-111">Используемых.</span><span class="sxs-lookup"><span data-stu-id="c2eba-111">-   Optional.</span></span> <span data-ttu-id="c2eba-112">Задает тип применяемого механизма обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="c2eba-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="c2eba-113">Значение по умолчанию — `Message`.</span><span class="sxs-lookup"><span data-stu-id="c2eba-113">The default is `Message`.</span></span><br /><span data-ttu-id="c2eba-114">— Этот атрибут имеет тип <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="c2eba-114">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="c2eba-115">Атрибут Mode</span><span class="sxs-lookup"><span data-stu-id="c2eba-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="c2eba-116">Значение</span><span class="sxs-lookup"><span data-stu-id="c2eba-116">Value</span></span>|<span data-ttu-id="c2eba-117">Описание</span><span class="sxs-lookup"><span data-stu-id="c2eba-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="c2eba-118">None</span><span class="sxs-lookup"><span data-stu-id="c2eba-118">None</span></span>|<span data-ttu-id="c2eba-119">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="c2eba-119">Security is disabled.</span></span>|  
|<span data-ttu-id="c2eba-120">Транспорт</span><span class="sxs-lookup"><span data-stu-id="c2eba-120">Transport</span></span>|<span data-ttu-id="c2eba-121">Безопасность обеспечивается с помощью протокола HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c2eba-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="c2eba-122">Необходимо настроить службу с использованием SSL-сертификата.</span><span class="sxs-lookup"><span data-stu-id="c2eba-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="c2eba-123">Сообщение полностью защищено с помощью HTTPS, а проверка подлинности выполняется клиентом с помощью SSL-сертификата службы.</span><span class="sxs-lookup"><span data-stu-id="c2eba-123">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="c2eba-124">Проверка подлинности клиента контролируется посредством атрибута `ClientCredentials`.</span><span class="sxs-lookup"><span data-stu-id="c2eba-124">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="c2eba-125">объекта [\<transport>](transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="c2eba-125">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="c2eba-126">Сообщение</span><span class="sxs-lookup"><span data-stu-id="c2eba-126">Message</span></span>|<span data-ttu-id="c2eba-127">Безопасность обеспечивается с помощью средств безопасности сообщений SOAP.</span><span class="sxs-lookup"><span data-stu-id="c2eba-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="c2eba-128">По умолчанию текст сообщений SOAP шифруется и подписывается.</span><span class="sxs-lookup"><span data-stu-id="c2eba-128">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="c2eba-129">Этот режим предоставляет множество возможностей, например сведения о доступности учетных данных службы для клиентов на внештатных каналах, об используемом наборе алгоритмов и об уровне защиты, применяемом к тексту сообщения через свойство Security.Message.</span><span class="sxs-lookup"><span data-stu-id="c2eba-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="c2eba-130">Проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="c2eba-130">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="c2eba-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="c2eba-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="c2eba-132">В данном режиме HTTPS обеспечивает целостность, конфиденциальность и проверку подлинности сервера, а механизм безопасности сообщений SOAP обеспечивает проверку подлинности клиента.</span><span class="sxs-lookup"><span data-stu-id="c2eba-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="c2eba-133">По умолчанию проверка подлинности клиента выполняется один раз за сеанс, и результаты проверки сохраняются в кэше на протяжении всего сеанса.</span><span class="sxs-lookup"><span data-stu-id="c2eba-133">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c2eba-134">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="c2eba-134">Child Elements</span></span>  
  
|<span data-ttu-id="c2eba-135">Элемент</span><span class="sxs-lookup"><span data-stu-id="c2eba-135">Element</span></span>|<span data-ttu-id="c2eba-136">Описание</span><span class="sxs-lookup"><span data-stu-id="c2eba-136">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="c2eba-137">Определяет параметры безопасности транспорта.</span><span class="sxs-lookup"><span data-stu-id="c2eba-137">Defines the transport security settings.</span></span> <span data-ttu-id="c2eba-138">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>.</span><span class="sxs-lookup"><span data-stu-id="c2eba-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="c2eba-139">Определяет параметры безопасности сообщения.</span><span class="sxs-lookup"><span data-stu-id="c2eba-139">Defines the security settings for the message.</span></span> <span data-ttu-id="c2eba-140">Этот элемент соответствует типу <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>.</span><span class="sxs-lookup"><span data-stu-id="c2eba-140">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c2eba-141">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="c2eba-141">Parent Elements</span></span>  
  
|<span data-ttu-id="c2eba-142">Элемент</span><span class="sxs-lookup"><span data-stu-id="c2eba-142">Element</span></span>|<span data-ttu-id="c2eba-143">Описание</span><span class="sxs-lookup"><span data-stu-id="c2eba-143">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="c2eba-144">Привязка безопасности для приложений транспорта HTTP.</span><span class="sxs-lookup"><span data-stu-id="c2eba-144">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2eba-145">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2eba-145">Remarks</span></span>  
 <span data-ttu-id="c2eba-146">Класс WSHttpBinding предназначен для взаимодействия со службами, реализующими спецификации WS-\*.</span><span class="sxs-lookup"><span data-stu-id="c2eba-146">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="c2eba-147">Безопасность транспорта для этой привязки обеспечивается посредством протокола SSL по протоколам HTTP или HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c2eba-147">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2eba-148">См. также</span><span class="sxs-lookup"><span data-stu-id="c2eba-148">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="c2eba-149">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c2eba-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="c2eba-150">Привязки</span><span class="sxs-lookup"><span data-stu-id="c2eba-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="c2eba-151">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="c2eba-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="c2eba-152">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="c2eba-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
