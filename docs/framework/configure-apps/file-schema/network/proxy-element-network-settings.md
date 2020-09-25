---
title: Элемент <proxy> (параметры сети)
description: <proxy>Элемент Параметры сети определяет параметры прокси-сервера в .NET Framework. Эта статья содержит пример.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/proxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#proxy
helpviewer_keywords:
- <proxy> element
- proxy element
ms.assetid: 37a548d8-fade-4ac5-82ec-b49b6c6cb22a
ms.openlocfilehash: 54b324dcd27d5827159bc2d773365e388a367d26
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91190219"
---
# <a name="proxy-element-network-settings"></a><span data-ttu-id="f051a-104">Элемент \<proxy> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="f051a-104">\<proxy> Element (Network Settings)</span></span>

<span data-ttu-id="f051a-105">Определяет прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="f051a-105">Defines a proxy server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<defaultProxy>**](defaultproxy-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<proxy>**

## <a name="syntax"></a><span data-ttu-id="f051a-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f051a-106">Syntax</span></span>  
  
```xml  
<proxy
  autoDetect="True|False|Unspecified"
  bypassonlocal="True|False|Unspecified"
  proxyaddress="uriString"
  scriptLocation="uriString"
  usesystemdefault="True|False|Unspecified"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f051a-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f051a-107">Attributes and Elements</span></span>  

 <span data-ttu-id="f051a-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f051a-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f051a-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f051a-109">Attributes</span></span>  
  
|<span data-ttu-id="f051a-110">**Attribute**</span><span class="sxs-lookup"><span data-stu-id="f051a-110">**Attribute**</span></span>|<span data-ttu-id="f051a-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f051a-111">**Description**</span></span>|  
|-------------------|---------------------|  
|`autoDetect`|<span data-ttu-id="f051a-112">Указывает, обнаруживается ли прокси-сервер автоматически.</span><span class="sxs-lookup"><span data-stu-id="f051a-112">Specifies whether the proxy is automatically detected.</span></span> <span data-ttu-id="f051a-113">Значение по умолчанию — `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="f051a-113">The default value is `Unspecified`.</span></span>|  
|`bypassonlocal`|<span data-ttu-id="f051a-114">Указывает, используется ли прокси-сервер для локальных ресурсов.</span><span class="sxs-lookup"><span data-stu-id="f051a-114">Specifies whether the proxy is bypassed for local resources.</span></span> <span data-ttu-id="f051a-115">Локальные ресурсы включают локальный сервер ( `http://localhost` , `http://loopback` или `http://127.0.0.1` ) и URI без точки ( `http://webserver` ).</span><span class="sxs-lookup"><span data-stu-id="f051a-115">Local resources include the local server (`http://localhost`, `http://loopback`, or `http://127.0.0.1`) and a URI without a period (`http://webserver`).</span></span> <span data-ttu-id="f051a-116">Значение по умолчанию — `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="f051a-116">The default value is `Unspecified`.</span></span>|  
|`proxyaddress`|<span data-ttu-id="f051a-117">Указывает используемый URI прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="f051a-117">Specifies the proxy URI to use.</span></span>|  
|`scriptLocation`|<span data-ttu-id="f051a-118">Указывает расположение скрипта конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f051a-118">Specifies the location of the configuration script.</span></span> <span data-ttu-id="f051a-119">Не используйте `bypassonlocal` атрибут с этим атрибутом.</span><span class="sxs-lookup"><span data-stu-id="f051a-119">Do not use the `bypassonlocal` attribute with this attribute.</span></span> |  
|`usesystemdefault`|<span data-ttu-id="f051a-120">Указывает, следует ли использовать параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="f051a-120">Specifies whether to use Internet Explorer proxy settings.</span></span> <span data-ttu-id="f051a-121">Если задано значение `True` , последующие атрибуты будут переопределять параметры прокси-сервера Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="f051a-121">If set to `True`, subsequent attributes will override Internet Explorer proxy settings.</span></span> <span data-ttu-id="f051a-122">Значение по умолчанию — `Unspecified`.</span><span class="sxs-lookup"><span data-stu-id="f051a-122">The default value is `Unspecified`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f051a-123">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f051a-123">Child Elements</span></span>  

 <span data-ttu-id="f051a-124">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f051a-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f051a-125">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f051a-125">Parent Elements</span></span>  
  
|<span data-ttu-id="f051a-126">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="f051a-126">**Element**</span></span>|<span data-ttu-id="f051a-127">**Описание**</span><span class="sxs-lookup"><span data-stu-id="f051a-127">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="f051a-128">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="f051a-128">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="f051a-129">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="f051a-129">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="text-value"></a><span data-ttu-id="f051a-130">Текстовое значение</span><span class="sxs-lookup"><span data-stu-id="f051a-130">Text Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f051a-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="f051a-131">Remarks</span></span>  

 <span data-ttu-id="f051a-132">`proxy`Элемент определяет прокси-сервер для приложения.</span><span class="sxs-lookup"><span data-stu-id="f051a-132">The `proxy` element defines a proxy server for an application.</span></span> <span data-ttu-id="f051a-133">Если этот элемент отсутствует в файле конфигурации, .NET Framework будет использовать параметры прокси-сервера в Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="f051a-133">If this element is missing from the configuration file, then the .NET Framework will use the proxy settings in Internet Explorer.</span></span>  
  
 <span data-ttu-id="f051a-134">Значение `proxyaddress` атрибута должно представлять собой универсальный код ресурса (URI) правильного формата.</span><span class="sxs-lookup"><span data-stu-id="f051a-134">The value for the `proxyaddress` attribute should be a well-formed Uniform Resource Indicator (URI).</span></span>  
  
 <span data-ttu-id="f051a-135">`scriptLocation`Атрибут относится к автоматическому обнаружению скриптов конфигурации прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="f051a-135">The `scriptLocation` attribute refers to the automatic detection of proxy configuration scripts.</span></span> <span data-ttu-id="f051a-136"><xref:System.Net.WebProxy>Класс будет пытаться разместить скрипт конфигурации (обычно с именем WPAD. dat), если в Internet Explorer выбран параметр **использовать скрипт автоматической настройки** .</span><span class="sxs-lookup"><span data-stu-id="f051a-136">The <xref:System.Net.WebProxy> class will attempt to locate a configuration script (usually named Wpad.dat) when the **Use automatic configuration script** option is selected in Internet Explorer.</span></span> <span data-ttu-id="f051a-137">Если `bypassonlocal` для задано любое значение, `scriptLocation` то параметр игнорируется.</span><span class="sxs-lookup"><span data-stu-id="f051a-137">If `bypassonlocal` is set to any value, `scriptLocation` is ignored.</span></span>
  
 <span data-ttu-id="f051a-138">Используйте `usesystemdefault` атрибут для приложений .NET Framework версии 1,1, которые переносятся на версию 2,0.</span><span class="sxs-lookup"><span data-stu-id="f051a-138">Use the `usesystemdefault` attribute for .NET Framework version 1.1 applications that are migrating to version 2.0.</span></span>  
  
 <span data-ttu-id="f051a-139">Если `proxyaddress` атрибут указывает на недопустимый прокси-сервер по умолчанию, возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="f051a-139">An exception is thrown if the `proxyaddress` attribute specifies an invalid default proxy.</span></span> <span data-ttu-id="f051a-140">Свойство <xref:System.Exception.InnerException%2A> исключения должно иметь дополнительные сведения о первопричине ошибки.</span><span class="sxs-lookup"><span data-stu-id="f051a-140">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="f051a-141">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="f051a-141">Configuration Files</span></span>  

 <span data-ttu-id="f051a-142">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="f051a-142">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f051a-143">Пример</span><span class="sxs-lookup"><span data-stu-id="f051a-143">Example</span></span>  

 <span data-ttu-id="f051a-144">В следующем примере используются значения по умолчанию из прокси-сервера Internet Explorer, указывается адрес прокси-сервера и выполняется обход прокси-сервера для локального доступа.</span><span class="sxs-lookup"><span data-stu-id="f051a-144">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="True"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="True"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f051a-145">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f051a-145">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="f051a-146">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="f051a-146">Network Settings Schema</span></span>](index.md)
