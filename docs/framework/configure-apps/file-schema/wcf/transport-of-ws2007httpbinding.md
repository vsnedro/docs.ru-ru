---
title: <transport> из <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 0cd20c607b0c4ddd3ecfd806d38ba63b4a5c5a25
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732763"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="2c15b-102">\<transport> из \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="2c15b-102">\<transport> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="2c15b-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="2c15b-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="2c15b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c15b-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="2c15b-105">Type</span><span class="sxs-lookup"><span data-stu-id="2c15b-105">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2c15b-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2c15b-106">Attributes and Elements</span></span>  
 <span data-ttu-id="2c15b-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2c15b-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2c15b-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2c15b-108">Attributes</span></span>  
  
|<span data-ttu-id="2c15b-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="2c15b-109">Attribute</span></span>|<span data-ttu-id="2c15b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="2c15b-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="2c15b-111">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="2c15b-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="2c15b-112">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2c15b-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="2c15b-113">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="2c15b-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="2c15b-114">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="2c15b-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="2c15b-115">Область проверки подлинности, используемая для дайджест-проверки подлинности или базовой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c15b-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="2c15b-116">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="2c15b-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="2c15b-117">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c15b-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="2c15b-118">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="2c15b-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="2c15b-119">Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.</span><span class="sxs-lookup"><span data-stu-id="2c15b-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="2c15b-120">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="2c15b-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2c15b-121">Значение</span><span class="sxs-lookup"><span data-stu-id="2c15b-121">Value</span></span>|<span data-ttu-id="2c15b-122">Описание</span><span class="sxs-lookup"><span data-stu-id="2c15b-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2c15b-123">None</span><span class="sxs-lookup"><span data-stu-id="2c15b-123">None</span></span>|<span data-ttu-id="2c15b-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="2c15b-124">Security is disabled.</span></span>|  
|<span data-ttu-id="2c15b-125">Basic</span><span class="sxs-lookup"><span data-stu-id="2c15b-125">Basic</span></span>|<span data-ttu-id="2c15b-126">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c15b-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="2c15b-127">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="2c15b-127">Digest</span></span>|<span data-ttu-id="2c15b-128">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c15b-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="2c15b-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2c15b-129">Ntlm</span></span>|<span data-ttu-id="2c15b-130">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="2c15b-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="2c15b-131">Windows</span><span class="sxs-lookup"><span data-stu-id="2c15b-131">Windows</span></span>|<span data-ttu-id="2c15b-132">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="2c15b-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="2c15b-133">Сертификат</span><span class="sxs-lookup"><span data-stu-id="2c15b-133">Certificate</span></span>|<span data-ttu-id="2c15b-134">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="2c15b-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="2c15b-135">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="2c15b-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="2c15b-136">Значение</span><span class="sxs-lookup"><span data-stu-id="2c15b-136">Value</span></span>|<span data-ttu-id="2c15b-137">Описание</span><span class="sxs-lookup"><span data-stu-id="2c15b-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2c15b-138">None</span><span class="sxs-lookup"><span data-stu-id="2c15b-138">None</span></span>|<span data-ttu-id="2c15b-139">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="2c15b-139">Security is disabled.</span></span>|  
|<span data-ttu-id="2c15b-140">Basic</span><span class="sxs-lookup"><span data-stu-id="2c15b-140">Basic</span></span>|<span data-ttu-id="2c15b-141">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c15b-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="2c15b-142">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="2c15b-142">Digest</span></span>|<span data-ttu-id="2c15b-143">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="2c15b-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="2c15b-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="2c15b-144">Ntlm</span></span>|<span data-ttu-id="2c15b-145">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="2c15b-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="2c15b-146">Windows</span><span class="sxs-lookup"><span data-stu-id="2c15b-146">Windows</span></span>|<span data-ttu-id="2c15b-147">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="2c15b-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="2c15b-148">Сертификат</span><span class="sxs-lookup"><span data-stu-id="2c15b-148">Certificate</span></span>|<span data-ttu-id="2c15b-149">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="2c15b-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2c15b-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2c15b-150">Child Elements</span></span>  
 <span data-ttu-id="2c15b-151">Нет</span><span class="sxs-lookup"><span data-stu-id="2c15b-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2c15b-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2c15b-152">Parent Elements</span></span>  
  
|<span data-ttu-id="2c15b-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="2c15b-153">Element</span></span>|<span data-ttu-id="2c15b-154">Описание</span><span class="sxs-lookup"><span data-stu-id="2c15b-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="2c15b-155">Представляет возможности безопасности [\<ws2007HttpBinding>](ws2007httpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="2c15b-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c15b-156">См. также</span><span class="sxs-lookup"><span data-stu-id="2c15b-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="2c15b-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2c15b-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2c15b-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="2c15b-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2c15b-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="2c15b-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2c15b-160">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="2c15b-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
