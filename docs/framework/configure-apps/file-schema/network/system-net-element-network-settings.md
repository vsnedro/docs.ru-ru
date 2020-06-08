---
title: Элемент <system.Net> (параметры сети)
description: Элемент Параметры сети <system.Net> содержит параметры, указывающие, как .NET Framework подключается к параметрам сети в .NET Framework.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 9f18c7a3586948c03391d609f437e216a91bc27f
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504489"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="46da9-103">Элемент \<system.Net> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="46da9-103">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="46da9-104">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="46da9-104">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="46da9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="46da9-105">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46da9-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="46da9-106">Attributes and Elements</span></span>  
 <span data-ttu-id="46da9-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="46da9-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46da9-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="46da9-108">Attributes</span></span>  
 <span data-ttu-id="46da9-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="46da9-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46da9-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="46da9-110">Child Elements</span></span>  
  
|<span data-ttu-id="46da9-111">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="46da9-111">**Element**</span></span>|<span data-ttu-id="46da9-112">**Описание**</span><span class="sxs-lookup"><span data-stu-id="46da9-112">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="46da9-113">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="46da9-113">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="46da9-114">Указывает модули, используемые для проверки подлинности интернет запросов.</span><span class="sxs-lookup"><span data-stu-id="46da9-114">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="46da9-115">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="46da9-115">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="46da9-116">Указывает максимальное число подключений к узлу в Интернете.</span><span class="sxs-lookup"><span data-stu-id="46da9-116">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="46da9-117">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="46da9-117">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="46da9-118">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="46da9-118">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="46da9-119">маилсеттингс</span><span class="sxs-lookup"><span data-stu-id="46da9-119">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="46da9-120">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="46da9-120">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="46da9-121">requestCaching</span><span class="sxs-lookup"><span data-stu-id="46da9-121">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="46da9-122">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="46da9-122">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="46da9-123">параметры</span><span class="sxs-lookup"><span data-stu-id="46da9-123">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="46da9-124">Настраивает основные сетевые параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="46da9-124">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="46da9-125">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="46da9-125">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="46da9-126">Указывает модули, используемые для запроса информации от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="46da9-126">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46da9-127">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="46da9-127">Parent Elements</span></span>  
  
|<span data-ttu-id="46da9-128">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="46da9-128">**Element**</span></span>|<span data-ttu-id="46da9-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="46da9-129">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="46da9-130">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="46da9-130">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="46da9-131">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="46da9-131">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46da9-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="46da9-132">Remarks</span></span>  
 <span data-ttu-id="46da9-133">[\<system.net>](system-net-element-network-settings.md)Элемент содержит параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="46da9-133">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="46da9-134">Параметры настройки модулей проверки подлинности, управления подключениями, параметров почты, прокси-сервера и модулей запросов Интернета для получения данных от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="46da9-134">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46da9-135">Пример</span><span class="sxs-lookup"><span data-stu-id="46da9-135">Example</span></span>  
 <span data-ttu-id="46da9-136">В следующем примере показана типичная конфигурация, используемая <xref:System.Net> классами.</span><span class="sxs-lookup"><span data-stu-id="46da9-136">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <authenticationModules>  
      <add type="System.Net.DigestClient" />  
      <add type="System.Net.NegotiateClient" />  
      <add type="System.Net.KerberosClient" />  
      <add type="System.Net.NtlmClient" />  
      <add type="System.Net.BasicClient" />  
    </authenticationModules>  
    <connectionManagement>  
      <add address="*" maxconnection="2" />  
    </connectionManagement>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        bypassonlocal="true"  
      />  
    </defaultProxy>  
    <webRequestModules>  
      <add prefix="http"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="https"  
           type="System.Net.HttpRequestCreator"  
      />  
      <add prefix="file"  
           type="System.Net.FileWebRequestCreator"  
      />  
    </webRequestModules>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="46da9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="46da9-137">See also</span></span>

- [<span data-ttu-id="46da9-138">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="46da9-138">Network Settings Schema</span></span>](index.md)
