---
title: Элемент <proxy> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 590ea747c2fa9e5e85e5e9d05f6fb80fe60251d3
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154794"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="4041e-102">Элемент \<proxy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="4041e-102">\<proxy> Element (Network Settings)</span></span>
<span data-ttu-id="4041e-103">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="4041e-103">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="4041e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4041e-104">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="true|false|unspecified"
  bypassonlocal="true|false|unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="true|false|unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4041e-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4041e-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4041e-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4041e-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4041e-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4041e-107">Attributes</span></span>  
  
|<span data-ttu-id="4041e-108">**Attribute (XElement Dynamic Property)** (Attribute (динамическое свойство XElement))</span><span class="sxs-lookup"><span data-stu-id="4041e-108">**Attribute**</span></span>|<span data-ttu-id="4041e-109">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4041e-109">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="4041e-110">Указывает, обнаруживается ли прокси-сервер автоматически.</span><span class="sxs-lookup"><span data-stu-id="4041e-110">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="4041e-111">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="4041e-111">The default value is `unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="4041e-112">Указывает, используется ли прокси-сервер для локальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="4041e-112">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="4041e-113">Локальные ресурсы включают локальный сервер ( `http://localhost` , `http://loopback` или `http://127.0.0.1` ) и URI без точки ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="4041e-113">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="4041e-114">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="4041e-114">The default value is `unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="4041e-115">Указывает используемый URI прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="4041e-115">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="4041e-116">Указывает расположение скрипта конфигурации.</span><span class="sxs-lookup"><span data-stu-id="4041e-116">Specifies the location of the configuration script.</span></span> <span data-ttu-id="4041e-117">Не используйте `bypassonlocal` атрибут с этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="4041e-117">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="4041e-118">Указывает, следует ли использовать параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4041e-118">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="4041e-119">Если задано значение `true` , последующие атрибуты будут переопределять параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4041e-119">If set to `true`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="4041e-120">Значение по умолчанию — `unspecified`.</span><span class="sxs-lookup"><span data-stu-id="4041e-120">The default value is `unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4041e-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4041e-121">Child Elements</span></span>  
 <span data-ttu-id="4041e-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4041e-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4041e-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4041e-123">Parent Elements</span></span>  
  
|<span data-ttu-id="4041e-124">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="4041e-124">**Element**</span></span>|<span data-ttu-id="4041e-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4041e-125">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="4041e-126">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="4041e-126">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="4041e-127">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="4041e-127">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="4041e-128">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="4041e-128">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4041e-129">Примечания</span><span class="sxs-lookup"><span data-stu-id="4041e-129">Remarks</span></span>  
 <span data-ttu-id="4041e-130">`proxy`Элемент определяет прокси-сервер для приложения.</span><span class="sxs-lookup"><span data-stu-id="4041e-130">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="4041e-131">Если этот элемент отсутствует в файле конфигурации, .NET Framework будет использовать параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="4041e-131">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="4041e-132">Значение `proxyaddress` атрибута должно представлять собой универсальный код ресурса (URI) правильного формата.</span><span class="sxs-lookup"><span data-stu-id="4041e-132">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="4041e-133">`scriptLocation`Атрибут относится к автоматическому обнаружению скриптов конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="4041e-133">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="4041e-134"><xref:System.Net.WebProxy>Класс будет пытаться разместить скрипт конфигурации (обычно с именем WPAD. dat), если в Internet Explorer выбран параметр **использовать скрипт автоматической настройки** .</span><span class="sxs-lookup"><span data-stu-id="4041e-134">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="4041e-135">Если `bypassonlocal` для задано любое значение, `scriptLocation` то параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="4041e-135">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="4041e-136">Используйте `usesystemdefault` атрибут для приложений .NET Framework версии 1,1, которые переносятся на версию 2,0.</span><span class="sxs-lookup"><span data-stu-id="4041e-136">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="4041e-137">Если `proxyaddress` атрибут указывает на недопустимый прокси-сервер по умолчанию, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="4041e-137">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="4041e-138">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="4041e-138">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="4041e-139">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="4041e-139">Configuration Files</span></span>  
 <span data-ttu-id="4041e-140">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="4041e-140">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4041e-141">Пример</span><span class="sxs-lookup"><span data-stu-id="4041e-141">Example</span></span>  
 <span data-ttu-id="4041e-142">В следующем примере используются значения по умолчанию из прокси-сервера Internet Explorer, указывается адрес прокси-сервера и выполняется обход прокси-сервера для локального доступа.</span><span class="sxs-lookup"><span data-stu-id="4041e-142">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4041e-143">См. также</span><span class="sxs-lookup"><span data-stu-id="4041e-143">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="4041e-144">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="4041e-144">Network Settings Schema</span></span>](index.md)
