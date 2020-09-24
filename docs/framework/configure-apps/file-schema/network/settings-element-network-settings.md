---
title: Элемент <settings> (параметры сети)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#settings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/settings
helpviewer_keywords:
- settings element
- <settings> element
ms.assetid: 189ce989-c39b-427d-b004-6b82a668b931
ms.openlocfilehash: c5fe0b9eccd1c429c0041fcfab06b0cc20a20aa2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91167279"
---
# <a name="settings-element-network-settings"></a><span data-ttu-id="410a6-102">Элемент \<settings> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="410a6-102">\<settings> Element (Network Settings)</span></span>

<span data-ttu-id="410a6-103">Настраивает основные параметры сети для пространства имен <xref:System.Net?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="410a6-103">Configures basic network options for the <xref:System.Net?displayProperty=nameWithType> namespace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<settings>**

## <a name="syntax"></a><span data-ttu-id="410a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="410a6-104">Syntax</span></span>  
  
```xml  
<settings>  
  <httpListener>...</httpListener>  
  <httpWebRequest>...</httpWebRequest>  
  <ipv6>...</ipv6>  
  <performanceCounters>...</performanceCounters>  
  <servicePointManager>...</servicePointManager>  
  <socket>...</socket>  
  <webProxyScript>...</webProxyScript>  
</settings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="410a6-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="410a6-105">Attributes and Elements</span></span>  

 <span data-ttu-id="410a6-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="410a6-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="410a6-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="410a6-107">Attributes</span></span>  

 <span data-ttu-id="410a6-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="410a6-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="410a6-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="410a6-109">Child Elements</span></span>  
  
|<span data-ttu-id="410a6-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="410a6-110">Element</span></span>|<span data-ttu-id="410a6-111">Описание</span><span class="sxs-lookup"><span data-stu-id="410a6-111">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="410a6-112">httpListener</span><span class="sxs-lookup"><span data-stu-id="410a6-112">httpListener</span></span>](httplistener-element-network-settings.md)|<span data-ttu-id="410a6-113">Настраивает параметры, используемые <xref:System.Net.HttpListener> классом.</span><span class="sxs-lookup"><span data-stu-id="410a6-113">Customizes parameters used by the <xref:System.Net.HttpListener> class.</span></span>|  
|[<span data-ttu-id="410a6-114">httpWebRequest</span><span class="sxs-lookup"><span data-stu-id="410a6-114">httpWebRequest</span></span>](httpwebrequest-element-network-settings.md)|<span data-ttu-id="410a6-115">Настраивает параметры веб-запроса.</span><span class="sxs-lookup"><span data-stu-id="410a6-115">Customizes Web request parameters.</span></span>|  
|[<span data-ttu-id="410a6-116">Протокол</span><span class="sxs-lookup"><span data-stu-id="410a6-116">ipv6</span></span>](ipv6-element-network-settings.md)|<span data-ttu-id="410a6-117">Включает поддержку протокола IP версии 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="410a6-117">Enables Internet Protocol version 6 (IPv6) support.</span></span>|  
|[<span data-ttu-id="410a6-118">Элемент \<performanceCounter> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="410a6-118">\<performanceCounter> Element (Network Settings)</span></span>](performancecounter-element-network-settings.md)|<span data-ttu-id="410a6-119">Включает счетчики производительности сети.</span><span class="sxs-lookup"><span data-stu-id="410a6-119">Enables network performance counters.</span></span>|  
|[<span data-ttu-id="410a6-120">servicePointManager</span><span class="sxs-lookup"><span data-stu-id="410a6-120">servicePointManager</span></span>](servicepointmanager-element-network-settings.md)|<span data-ttu-id="410a6-121">Настраивает подключения к сетевым ресурсам.</span><span class="sxs-lookup"><span data-stu-id="410a6-121">Configures connections to network resources.</span></span>|  
|[<span data-ttu-id="410a6-122">фиксатор</span><span class="sxs-lookup"><span data-stu-id="410a6-122">socket</span></span>](socket-element-network-settings.md)|<span data-ttu-id="410a6-123">Указывает, используют ли операции сокета порты завершения.</span><span class="sxs-lookup"><span data-stu-id="410a6-123">Specifies whether socket operations use completion ports.</span></span>|  
|[<span data-ttu-id="410a6-124">Элемент \<webProxyScript> (параметры сети)</span><span class="sxs-lookup"><span data-stu-id="410a6-124">\<webProxyScript> Element (Network Settings)</span></span>](webproxyscript-element-network-settings.md)|<span data-ttu-id="410a6-125">Настраивает характеристики сценария, используемого для обнаружения веб-прокси.</span><span class="sxs-lookup"><span data-stu-id="410a6-125">Configures the characteristics of the script used to discover Web proxies.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="410a6-126">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="410a6-126">Parent Elements</span></span>  
  
|<span data-ttu-id="410a6-127">Элемент</span><span class="sxs-lookup"><span data-stu-id="410a6-127">Element</span></span>|<span data-ttu-id="410a6-128">Описание</span><span class="sxs-lookup"><span data-stu-id="410a6-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="410a6-129">system.net</span><span class="sxs-lookup"><span data-stu-id="410a6-129">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="410a6-130">Содержит параметры сети, определяющие способ подключения .NET Framework к Интернету.</span><span class="sxs-lookup"><span data-stu-id="410a6-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="410a6-131">Remarks</span><span class="sxs-lookup"><span data-stu-id="410a6-131">Remarks</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="410a6-132">Файлы конфигурации</span><span class="sxs-lookup"><span data-stu-id="410a6-132">Configuration Files</span></span>  

 <span data-ttu-id="410a6-133">Этот элемент может использоваться в файле конфигурации приложения или в файле конфигурации компьютера (Machine.config).</span><span class="sxs-lookup"><span data-stu-id="410a6-133">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="410a6-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="410a6-134">See also</span></span>

- <xref:System.Net?displayProperty=nameWithType>
- [<span data-ttu-id="410a6-135">Схема параметров сети</span><span class="sxs-lookup"><span data-stu-id="410a6-135">Network Settings Schema</span></span>](index.md)
