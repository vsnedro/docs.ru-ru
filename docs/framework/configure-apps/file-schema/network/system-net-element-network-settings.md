---
title: Элемент <system.Net> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.Net
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.Net
helpviewer_keywords:
- system.Net element
- <system.Net> element
ms.assetid: 52de4d6c-b24d-44aa-ba7d-6b5061f1357e
ms.openlocfilehash: 88098f2afaad9728e38c4f9935b45f45826a0ca9
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154560"
---
# <a name="systemnet-element-network-settings"></a><span data-ttu-id="49089-102">Элемент \<system.Net> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="49089-102">\<system.Net> Element (Network Settings)</span></span>
<span data-ttu-id="49089-103">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="49089-103">Contains settings that specify how the .NET Framework connects to the network.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.net>**  
  
## <a name="syntax"></a><span data-ttu-id="49089-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49089-104">Syntax</span></span>  
  
```xml  
<system.net>
</system.net>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="49089-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="49089-105">Attributes and Elements</span></span>  
 <span data-ttu-id="49089-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="49089-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="49089-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="49089-107">Attributes</span></span>  
 <span data-ttu-id="49089-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="49089-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="49089-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="49089-109">Child Elements</span></span>  
  
|<span data-ttu-id="49089-110">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="49089-110">**Element**</span></span>|<span data-ttu-id="49089-111">**Описание**</span><span class="sxs-lookup"><span data-stu-id="49089-111">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="49089-112">authenticationModules</span><span class="sxs-lookup"><span data-stu-id="49089-112">authenticationModules</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="49089-113">Указывает модули, используемые для проверки подлинности интернет запросов.</span><span class="sxs-lookup"><span data-stu-id="49089-113">Specifies modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="49089-114">connectionManagement</span><span class="sxs-lookup"><span data-stu-id="49089-114">connectionManagement</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="49089-115">Указывает максимальное число подключений к узлу в Интернете.</span><span class="sxs-lookup"><span data-stu-id="49089-115">Specifies the maximum number of connections to an Internet host.</span></span>|  
|[<span data-ttu-id="49089-116">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="49089-116">defaultProxy</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="49089-117">Настраивает прокси-сервер протокола передачи гипертекста (HTTP).</span><span class="sxs-lookup"><span data-stu-id="49089-117">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
|[<span data-ttu-id="49089-118">маилсеттингс</span><span class="sxs-lookup"><span data-stu-id="49089-118">mailSettings</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="49089-119">Настраивает параметры отправки почты по протоколу SMTP.</span><span class="sxs-lookup"><span data-stu-id="49089-119">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
|[<span data-ttu-id="49089-120">requestCaching</span><span class="sxs-lookup"><span data-stu-id="49089-120">requestCaching</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="49089-121">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="49089-121">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="49089-122">параметры</span><span class="sxs-lookup"><span data-stu-id="49089-122">settings</span></span>](settings-element-network-settings.md)|<span data-ttu-id="49089-123">Настраивает основные сетевые параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="49089-123">Configures basic network options for classes in the <xref:System.Net> and related child namespaces.</span></span>|  
|[<span data-ttu-id="49089-124">webRequestModules</span><span class="sxs-lookup"><span data-stu-id="49089-124">webRequestModules</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="49089-125">Указывает модули, используемые для запроса информации от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="49089-125">Specifies modules to use to request information from Internet hosts.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="49089-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="49089-126">Parent Elements</span></span>  
  
|<span data-ttu-id="49089-127">**Элемент**</span><span class="sxs-lookup"><span data-stu-id="49089-127">**Element**</span></span>|<span data-ttu-id="49089-128">**Описание**</span><span class="sxs-lookup"><span data-stu-id="49089-128">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="49089-129">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="49089-129">configuration</span></span>](../configuration-element.md)|<span data-ttu-id="49089-130">Содержит параметры для всех пространств имен.</span><span class="sxs-lookup"><span data-stu-id="49089-130">Contains settings for all namespaces.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49089-131">Примечания</span><span class="sxs-lookup"><span data-stu-id="49089-131">Remarks</span></span>  
 <span data-ttu-id="49089-132">[\<system.net>](system-net-element-network-settings.md)Элемент содержит параметры для классов в <xref:System.Net> и связанных дочерних пространствах имен.</span><span class="sxs-lookup"><span data-stu-id="49089-132">The [\<system.net>](system-net-element-network-settings.md) element contains settings for classes in the <xref:System.Net> and related child namespaces.</span></span> <span data-ttu-id="49089-133">Параметры настройки модулей проверки подлинности, управления подключениями, параметров почты, прокси-сервера и модулей запросов Интернета для получения данных от узлов Интернета.</span><span class="sxs-lookup"><span data-stu-id="49089-133">The settings configure authentication modules, connection management, mail settings, the proxy server, and Internet request modules for receiving information from Internet hosts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49089-134">Пример</span><span class="sxs-lookup"><span data-stu-id="49089-134">Example</span></span>  
 <span data-ttu-id="49089-135">В следующем примере показана типичная конфигурация, используемая <xref:System.Net> классами.</span><span class="sxs-lookup"><span data-stu-id="49089-135">The following example shows a typical configuration used by <xref:System.Net> classes.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="49089-136">См. также</span><span class="sxs-lookup"><span data-stu-id="49089-136">See also</span></span>

- [<span data-ttu-id="49089-137">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="49089-137">Network Settings Schema</span></span>](index.md)
