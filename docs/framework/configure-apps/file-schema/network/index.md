---
title: Схема параметров сети
description: Сведения о схеме параметров сети, указывающих, как .NET Framework подключается к Интернету и обрабатывает URI.
ms.date: 03/30/2017
helpviewer_keywords:
- elements [.NET Framework], network configuration elements
- sending data, network configuration elements
- receiving data, network configuration elements
- configuration settings [.NET Framework], networks
- Internet, network configuration elements
- network configuration elements
- network settings
- connections [.NET Framework], network configuration elements
- network resources, network configuration elements
ms.assetid: f1de5a0f-76c5-4833-819f-5222b8146340
ms.openlocfilehash: 6a22d7f1608db2e8909d0ead11e9110ec8a8a2c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504580"
---
# <a name="network-settings-schema"></a><span data-ttu-id="37b97-103">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="37b97-103">Network Settings Schema</span></span>
<span data-ttu-id="37b97-104">Параметры сети определяют способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="37b97-104">Network settings specify how the .NET Framework connects to the Internet.</span></span>

<span data-ttu-id="37b97-105">\<system.net>Параметры указывают, как .NET Framework подключается к сети.</span><span class="sxs-lookup"><span data-stu-id="37b97-105">The \<system.net> settings specify how the .NET Framework connects to the network.</span></span> <span data-ttu-id="37b97-106">В следующей таблице описывается функция каждого дочернего элемента конфигурации в [ \<system.Net> элементе (параметры сети)](system-net-element-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="37b97-106">The following table describes the function of each child configuration element under the [\<system.Net> Element (Network Settings)](system-net-element-network-settings.md).</span></span>  
  
|<span data-ttu-id="37b97-107">Элемент</span><span class="sxs-lookup"><span data-stu-id="37b97-107">Element</span></span>|<span data-ttu-id="37b97-108">Описание</span><span class="sxs-lookup"><span data-stu-id="37b97-108">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37b97-109">\<authenticationModules>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="37b97-109">\<authenticationModules> Element (Network Settings)</span></span>](authenticationmodules-element-network-settings.md)|<span data-ttu-id="37b97-110">Определяет модули, используемые для проверки подлинности интернет-запросов.</span><span class="sxs-lookup"><span data-stu-id="37b97-110">Specifies the modules used to authenticate Internet requests.</span></span>|  
|[<span data-ttu-id="37b97-111">\<connectionManagement>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="37b97-111">\<connectionManagement> Element (Network Settings)</span></span>](connectionmanagement-element-network-settings.md)|<span data-ttu-id="37b97-112">Задает максимальное число подключений к узлам в Интернете.</span><span class="sxs-lookup"><span data-stu-id="37b97-112">Specifies the maximum number of connections to Internet hosts.</span></span>|  
|[<span data-ttu-id="37b97-113">\<defaultProxy>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="37b97-113">\<defaultProxy> Element (Network Settings)</span></span>](defaultproxy-element-network-settings.md)|<span data-ttu-id="37b97-114">Задает прокси-сервер, используемый для HTTP-запросов к Интернету.</span><span class="sxs-lookup"><span data-stu-id="37b97-114">Specifies the proxy server used for HTTP requests to the Internet.</span></span>|  
|[<span data-ttu-id="37b97-115">\<mailSettings>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="37b97-115">\<mailSettings> Element (Network Settings)</span></span>](mailsettings-element-network-settings.md)|<span data-ttu-id="37b97-116">Содержит параметры отправки почты.</span><span class="sxs-lookup"><span data-stu-id="37b97-116">Contains settings for mail sending options.</span></span>|  
|[<span data-ttu-id="37b97-117">\<requestCaching>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="37b97-117">\<requestCaching> Element (Network Settings)</span></span>](requestcaching-element-network-settings.md)|<span data-ttu-id="37b97-118">Управляет механизмом кэширования для сетевых запросов.</span><span class="sxs-lookup"><span data-stu-id="37b97-118">Controls the caching mechanism for network requests.</span></span>|  
|[<span data-ttu-id="37b97-119">\<webRequestModules>Элемент (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="37b97-119">\<webRequestModules> Element (Network Settings)</span></span>](webrequestmodules-element-network-settings.md)|<span data-ttu-id="37b97-120">Задает модули, используемые для запроса данных от узлов в Интернете.</span><span class="sxs-lookup"><span data-stu-id="37b97-120">Specifies the modules used to request information from Internet hosts.</span></span>|  
  
<span data-ttu-id="37b97-121">\<uri>Параметры определяют, как .NET Framework обрабатывает веб-адреса, выраженные с помощью универсальных идентификаторов ресурсов (URI).</span><span class="sxs-lookup"><span data-stu-id="37b97-121">The \<uri> settings specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span> <span data-ttu-id="37b97-122">В следующей таблице описывается функция каждого дочернего элемента конфигурации в [ \<uri> элементе (Параметры URI)](uri-element-uri-settings.md).</span><span class="sxs-lookup"><span data-stu-id="37b97-122">The following table describes the function of each child configuration element under the [\<uri> Element (Uri Settings)](uri-element-uri-settings.md).</span></span>  
  
|<span data-ttu-id="37b97-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="37b97-123">Element</span></span>|<span data-ttu-id="37b97-124">Описание</span><span class="sxs-lookup"><span data-stu-id="37b97-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="37b97-125">\<idn>Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="37b97-125">\<idn> Element (Uri Settings)</span></span>](idn-element-uri-settings.md)|<span data-ttu-id="37b97-126">Определяет, применяется ли к доменным именам анализ международных доменных имен (IDN).</span><span class="sxs-lookup"><span data-stu-id="37b97-126">Specifies if Internationalized Domain Name (IDN) parsing is applied to domain names.</span></span>|  
|[<span data-ttu-id="37b97-127">\<iriParsing>Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="37b97-127">\<iriParsing> Element (Uri Settings)</span></span>](iriparsing-element-uri-settings.md)|<span data-ttu-id="37b97-128">Определяет, применяется ли к <xref:System.Uri> анализ международных идентификаторов ресурсов (IRI) и применяются ли правила анализа IRI.</span><span class="sxs-lookup"><span data-stu-id="37b97-128">Specifies if International Resource Identifier (IRI) parsing is applied to a <xref:System.Uri> and whether IRI parsing rules should be applied.</span></span>|  
|[<span data-ttu-id="37b97-129">\<schemeSettings>Элемент (Параметры URI)</span><span class="sxs-lookup"><span data-stu-id="37b97-129">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="37b97-130">Определяет, как <xref:System.Uri> анализируется для определенных схем.</span><span class="sxs-lookup"><span data-stu-id="37b97-130">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="37b97-131">См. также</span><span class="sxs-lookup"><span data-stu-id="37b97-131">See also</span></span>

- [<span data-ttu-id="37b97-132">Настройка веб-приложений</span><span class="sxs-lookup"><span data-stu-id="37b97-132">Configuring Internet Applications</span></span>](../../../network-programming/configuring-internet-applications.md)
- [<span data-ttu-id="37b97-133">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="37b97-133">Configuration File Schema</span></span>](../index.md)
