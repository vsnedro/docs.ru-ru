---
title: <transport> из <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 1afeed62fcbf3b083d69a7cedb7eb80b81f5c17b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732735"
---
# <a name="transport-of-wshttpbinding"></a><span data-ttu-id="68eac-102">\<transport> из \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="68eac-102">\<transport> of \<wsHttpBinding></span></span>

<span data-ttu-id="68eac-103">Определяет параметры проверки подлинности для HTTP-транспорта.</span><span class="sxs-lookup"><span data-stu-id="68eac-103">Defines authentication settings for the HTTP transport.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  

## <a name="syntax"></a><span data-ttu-id="68eac-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68eac-104">Syntax</span></span>

```xml
<wsHttpBinding>
  <binding>
    <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"
                 proxyCredentialType="Basic|Digest|None|Ntlm|Windows"
                 realm="string" />
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</wsHttpBinding>
```

## <a name="type"></a><span data-ttu-id="68eac-105">Type</span><span class="sxs-lookup"><span data-stu-id="68eac-105">Type</span></span>

<xref:System.ServiceModel.HttpTransportSecurity>

## <a name="attributes-and-elements"></a><span data-ttu-id="68eac-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="68eac-106">Attributes and Elements</span></span>

<span data-ttu-id="68eac-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="68eac-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="68eac-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="68eac-108">Attributes</span></span>

|<span data-ttu-id="68eac-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="68eac-109">Attribute</span></span>|<span data-ttu-id="68eac-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="68eac-110">Description</span></span>|
|---------------|-----------------|
|`clientCredentialType`|<span data-ttu-id="68eac-111">Задает учетные данные, используемые для проверки подлинности клиента при подключении к службе.</span><span class="sxs-lookup"><span data-stu-id="68eac-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="68eac-112">Это атрибут типа <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="68eac-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|
|`proxyCredentialType`|<span data-ttu-id="68eac-113">Задает учетные данные, используемые для проверки подлинности клиента при подключении к прокси-серверу домена.</span><span class="sxs-lookup"><span data-stu-id="68eac-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="68eac-114">Это атрибут типа <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="68eac-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|
|`realm`|<span data-ttu-id="68eac-115">Строка, указывающая область проверки подлинности для обычной проверки подлинности или дайджест-проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="68eac-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="68eac-116">Значением по умолчанию является пустая строка.</span><span class="sxs-lookup"><span data-stu-id="68eac-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="68eac-117">Область проверки подлинности задает по крайней мере имя основного узла, выполняющего проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="68eac-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="68eac-118">Она также может указывать коллекцию пользователей, которым разрешен доступ.</span><span class="sxs-lookup"><span data-stu-id="68eac-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="68eac-119">Пользователь может запросить область проверки подлинности, чтобы выяснить, какое из нескольких возможных сочетаний имен пользователей и паролей можно использовать.</span><span class="sxs-lookup"><span data-stu-id="68eac-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|
|`policyEnforcement`|<span data-ttu-id="68eac-120">Это перечисление указывает, когда следует применять <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy>.</span><span class="sxs-lookup"><span data-stu-id="68eac-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="68eac-121">1. Never — политика никогда не применяется (Расширенная защита отключена).</span><span class="sxs-lookup"><span data-stu-id="68eac-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="68eac-122">2. WhenSupported — политика применяется, только если клиент поддерживает расширенную защиту.</span><span class="sxs-lookup"><span data-stu-id="68eac-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="68eac-123">3. всегда — политика всегда применяется принудительно.</span><span class="sxs-lookup"><span data-stu-id="68eac-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="68eac-124">Клиенты, которые не поддерживают расширенную защиту, не смогут пройти проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="68eac-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|

## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="68eac-125">Атрибут clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="68eac-125">clientCredentialType Attribute</span></span>

|<span data-ttu-id="68eac-126">Значение</span><span class="sxs-lookup"><span data-stu-id="68eac-126">Value</span></span>|<span data-ttu-id="68eac-127">Описание</span><span class="sxs-lookup"><span data-stu-id="68eac-127">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="68eac-128">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="68eac-128">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="68eac-129">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="68eac-129">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="68eac-130">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="68eac-130">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="68eac-131">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="68eac-131">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="68eac-132">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="68eac-132">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="68eac-133">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="68eac-133">Uses X.509 certificates to authenticate the client.</span></span>|

## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="68eac-134">Атрибут proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="68eac-134">proxyCredentialType Attribute</span></span>

|<span data-ttu-id="68eac-135">Значение</span><span class="sxs-lookup"><span data-stu-id="68eac-135">Value</span></span>|<span data-ttu-id="68eac-136">Описание</span><span class="sxs-lookup"><span data-stu-id="68eac-136">Description</span></span>|
|-----------|-----------------|
|`None`|<span data-ttu-id="68eac-137">Режим безопасности отключен.</span><span class="sxs-lookup"><span data-stu-id="68eac-137">Security is disabled.</span></span>|
|`Basic`|<span data-ttu-id="68eac-138">Используется обычная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="68eac-138">Uses basic authentication.</span></span>|
|`Digest`|<span data-ttu-id="68eac-139">Используется дайджест-проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="68eac-139">Uses digest authentication.</span></span>|
|`Ntlm`|<span data-ttu-id="68eac-140">Используется проверка подлинности NTLM в качестве резервной в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="68eac-140">Uses NTLM as a fallback with a Windows domain.</span></span>|
|`Windows`|<span data-ttu-id="68eac-141">Используется встроенная проверка подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="68eac-141">Uses integrated Windows authentication.</span></span>|
|`Certificate`|<span data-ttu-id="68eac-142">Для проверки подлинности клиента используются сертификаты X.509.</span><span class="sxs-lookup"><span data-stu-id="68eac-142">Uses X.509 certificates to authenticate the client.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="68eac-143">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="68eac-143">Child Elements</span></span>

<span data-ttu-id="68eac-144">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="68eac-144">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="68eac-145">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="68eac-145">Parent Elements</span></span>

|<span data-ttu-id="68eac-146">Элемент</span><span class="sxs-lookup"><span data-stu-id="68eac-146">Element</span></span>|<span data-ttu-id="68eac-147">Описание</span><span class="sxs-lookup"><span data-stu-id="68eac-147">Description</span></span>|
|-------------|-----------------|
|[\<security>](security-of-wshttpbinding.md)|<span data-ttu-id="68eac-148">Представляет возможности безопасности [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="68eac-148">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>|

## <a name="see-also"></a><span data-ttu-id="68eac-149">См. также</span><span class="sxs-lookup"><span data-stu-id="68eac-149">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="68eac-150">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="68eac-150">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="68eac-151">Привязки</span><span class="sxs-lookup"><span data-stu-id="68eac-151">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="68eac-152">Настройка привязок, предоставляемых системой</span><span class="sxs-lookup"><span data-stu-id="68eac-152">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="68eac-153">Использование привязок для настройки служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="68eac-153">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
