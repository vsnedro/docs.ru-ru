---
title: <transport> из <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: b9efc732832a8862373b14f657796a59fb52c1a1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162118"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="527f4-102">\<transport> из \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="527f4-102">\<transport> of \<webHttpBinding></span></span>

<span data-ttu-id="527f4-103">Определяет параметры безопасности уровня транспорта для конечной точки службы, настроенной для получения запросов HTTP.</span><span class="sxs-lookup"><span data-stu-id="527f4-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="527f4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="527f4-104">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="527f4-105">Type</span><span class="sxs-lookup"><span data-stu-id="527f4-105">Type</span></span>  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="527f4-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="527f4-106">Attributes and Elements</span></span>  

 <span data-ttu-id="527f4-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="527f4-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="527f4-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="527f4-108">Attributes</span></span>  
  
|<span data-ttu-id="527f4-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="527f4-109">Attribute</span></span>|<span data-ttu-id="527f4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="527f4-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="527f4-111">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="527f4-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="527f4-112">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="527f4-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="527f4-113">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="527f4-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="527f4-114">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="527f4-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="527f4-115">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="527f4-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="527f4-116">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="527f4-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="527f4-117">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="527f4-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="527f4-118">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="527f4-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="527f4-119">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="527f4-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="527f4-120">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="527f4-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="527f4-121">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="527f4-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="527f4-122">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="527f4-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="527f4-123">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="527f4-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="527f4-124">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="527f4-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="527f4-125">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="527f4-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="527f4-126">Значение</span><span class="sxs-lookup"><span data-stu-id="527f4-126">Value</span></span>|<span data-ttu-id="527f4-127">Описание</span><span class="sxs-lookup"><span data-stu-id="527f4-127">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="527f4-128">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="527f4-128">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="527f4-129">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="527f4-129">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="527f4-130">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="527f4-130">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="527f4-131">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="527f4-131">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="527f4-132">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="527f4-132">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="527f4-133">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="527f4-133">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="527f4-134">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="527f4-134">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="527f4-135">Значение</span><span class="sxs-lookup"><span data-stu-id="527f4-135">Value</span></span>|<span data-ttu-id="527f4-136">Описание</span><span class="sxs-lookup"><span data-stu-id="527f4-136">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="527f4-137">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="527f4-137">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="527f4-138">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="527f4-138">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="527f4-139">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="527f4-139">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="527f4-140">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="527f4-140">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="527f4-141">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="527f4-141">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="527f4-142">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="527f4-142">Child Elements</span></span>  

 <span data-ttu-id="527f4-143">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="527f4-143">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="527f4-144">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="527f4-144">Parent Elements</span></span>  
  
|<span data-ttu-id="527f4-145">Элемент</span><span class="sxs-lookup"><span data-stu-id="527f4-145">Element</span></span>|<span data-ttu-id="527f4-146">Описание</span><span class="sxs-lookup"><span data-stu-id="527f4-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|<span data-ttu-id="527f4-147">Представляет возможности безопасности [\<wsHttpBinding>](wshttpbinding.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="527f4-147">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="527f4-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="527f4-148">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="527f4-149">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="527f4-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="527f4-150">Привязки</span><span class="sxs-lookup"><span data-stu-id="527f4-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="527f4-151">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="527f4-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="527f4-152">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="527f4-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="527f4-153">Модель веб-программирования HTTP WCF</span><span class="sxs-lookup"><span data-stu-id="527f4-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
