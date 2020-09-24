---
title: <transport> из <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: 692befa3-8b0b-4ec5-b601-755874e98eb0
ms.openlocfilehash: 60e8758d653848176ca3f287e253bd7990e78470
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162053"
---
# <a name="transport-of-ws2007httpbinding"></a><span data-ttu-id="05b8c-102">\<transport> из \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="05b8c-102">\<transport> of \<ws2007HttpBinding></span></span>

<span data-ttu-id="05b8c-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="05b8c-103">Defines authentication settings for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="05b8c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="05b8c-104">Syntax</span></span>  
  
```xml  
<transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
           proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
           realm="string" />
```  
  
## <a name="type"></a><span data-ttu-id="05b8c-105">Type</span><span class="sxs-lookup"><span data-stu-id="05b8c-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05b8c-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="05b8c-106">Attributes and Elements</span></span>  

 <span data-ttu-id="05b8c-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="05b8c-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05b8c-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="05b8c-108">Attributes</span></span>  
  
|<span data-ttu-id="05b8c-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="05b8c-109">Attribute</span></span>|<span data-ttu-id="05b8c-110">Описание</span><span class="sxs-lookup"><span data-stu-id="05b8c-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="05b8c-111">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="05b8c-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="05b8c-112">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="05b8c-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="05b8c-113">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="05b8c-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="05b8c-114">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="05b8c-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="05b8c-115">Область проверки подлинности, используемая для дайджест-проверки подлинности или базовой проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="05b8c-115">The authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="05b8c-116">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="05b8c-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="05b8c-117">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="05b8c-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="05b8c-118">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="05b8c-118">It can also specify a collection of users who have access.</span></span> <span data-ttu-id="05b8c-119">Пользователь может направить запрос к области проверки подлинности, чтобы определить, какие конкретно имя и пароль из нескольких возможных можно использовать.</span><span class="sxs-lookup"><span data-stu-id="05b8c-119">A user can query the authentication realm to determine which one of the several possible usernames and passwords can be used.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="05b8c-120">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="05b8c-120">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="05b8c-121">Значение</span><span class="sxs-lookup"><span data-stu-id="05b8c-121">Value</span></span>|<span data-ttu-id="05b8c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="05b8c-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="05b8c-123">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="05b8c-123">None</span></span>|<span data-ttu-id="05b8c-124">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="05b8c-124">Security is disabled.</span></span>|  
|<span data-ttu-id="05b8c-125">Basic</span><span class="sxs-lookup"><span data-stu-id="05b8c-125">Basic</span></span>|<span data-ttu-id="05b8c-126">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="05b8c-126">Uses basic authentication.</span></span>|  
|<span data-ttu-id="05b8c-127">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="05b8c-127">Digest</span></span>|<span data-ttu-id="05b8c-128">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="05b8c-128">Uses digest authentication.</span></span>|  
|<span data-ttu-id="05b8c-129">Ntlm</span><span class="sxs-lookup"><span data-stu-id="05b8c-129">Ntlm</span></span>|<span data-ttu-id="05b8c-130">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="05b8c-130">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="05b8c-131">Windows</span><span class="sxs-lookup"><span data-stu-id="05b8c-131">Windows</span></span>|<span data-ttu-id="05b8c-132">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="05b8c-132">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="05b8c-133">Сертификат</span><span class="sxs-lookup"><span data-stu-id="05b8c-133">Certificate</span></span>|<span data-ttu-id="05b8c-134">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="05b8c-134">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="05b8c-135">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="05b8c-135">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="05b8c-136">Значение</span><span class="sxs-lookup"><span data-stu-id="05b8c-136">Value</span></span>|<span data-ttu-id="05b8c-137">Описание</span><span class="sxs-lookup"><span data-stu-id="05b8c-137">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="05b8c-138">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="05b8c-138">None</span></span>|<span data-ttu-id="05b8c-139">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="05b8c-139">Security is disabled.</span></span>|  
|<span data-ttu-id="05b8c-140">Basic</span><span class="sxs-lookup"><span data-stu-id="05b8c-140">Basic</span></span>|<span data-ttu-id="05b8c-141">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="05b8c-141">Uses basic authentication.</span></span>|  
|<span data-ttu-id="05b8c-142">Digest (дайджест)</span><span class="sxs-lookup"><span data-stu-id="05b8c-142">Digest</span></span>|<span data-ttu-id="05b8c-143">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="05b8c-143">Uses digest authentication.</span></span>|  
|<span data-ttu-id="05b8c-144">Ntlm</span><span class="sxs-lookup"><span data-stu-id="05b8c-144">Ntlm</span></span>|<span data-ttu-id="05b8c-145">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="05b8c-145">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|<span data-ttu-id="05b8c-146">Windows</span><span class="sxs-lookup"><span data-stu-id="05b8c-146">Windows</span></span>|<span data-ttu-id="05b8c-147">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="05b8c-147">Uses integrated Windows authentication.</span></span>|  
|<span data-ttu-id="05b8c-148">Сертификат</span><span class="sxs-lookup"><span data-stu-id="05b8c-148">Certificate</span></span>|<span data-ttu-id="05b8c-149">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="05b8c-149">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05b8c-150">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="05b8c-150">Child Elements</span></span>  

 <span data-ttu-id="05b8c-151">Нет</span><span class="sxs-lookup"><span data-stu-id="05b8c-151">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05b8c-152">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="05b8c-152">Parent Elements</span></span>  
  
|<span data-ttu-id="05b8c-153">Элемент</span><span class="sxs-lookup"><span data-stu-id="05b8c-153">Element</span></span>|<span data-ttu-id="05b8c-154">Описание</span><span class="sxs-lookup"><span data-stu-id="05b8c-154">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-ws2007httpbinding.md)|<span data-ttu-id="05b8c-155">Представляет возможности безопасности [\<ws2007HttpBinding>](ws2007httpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="05b8c-155">Represents the security capabilities of the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="05b8c-156">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="05b8c-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpTransportSecurityElement>
- [<span data-ttu-id="05b8c-157">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="05b8c-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="05b8c-158">Привязки</span><span class="sxs-lookup"><span data-stu-id="05b8c-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="05b8c-159">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="05b8c-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="05b8c-160">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="05b8c-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
