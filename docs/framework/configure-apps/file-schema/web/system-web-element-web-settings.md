---
title: Элемент <system.web> (веб-параметры)
ms.date: 03/30/2017
helpviewer_keywords:
- Web.config configuration file [ASP.NET]
- system.Web element
- <system.Web> element
- ASP.NET configuration system
- configuration files [ASP.NET]
ms.assetid: 24c4cf4f-ad32-42b2-b040-8e4549e2855e
ms.openlocfilehash: b37b05bdf90630251cbfcf86751243a3a8b77663
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79152845"
---
# <a name="systemweb-element-web-settings"></a><span data-ttu-id="3a6a4-102">Элемент \<system.web> (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="3a6a4-102">\<system.web> Element (Web Settings)</span></span>
<span data-ttu-id="3a6a4-103">Содержит сведения о том, как уровень размещения ASP.NET управляет поведением всего процесса.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-103">Contains information about how the ASP.NET hosting layer manages process-wide behavior.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.web>**  
  
## <a name="syntax"></a><span data-ttu-id="3a6a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3a6a4-104">Syntax</span></span>  
  
```xml  
<system.web>  
</system.web>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3a6a4-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3a6a4-105">Attributes and Elements</span></span>  

<span data-ttu-id="3a6a4-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3a6a4-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3a6a4-107">Attributes</span></span>  

<span data-ttu-id="3a6a4-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3a6a4-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3a6a4-109">Child Elements</span></span>  
  
|<span data-ttu-id="3a6a4-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a6a4-110">Element</span></span>|<span data-ttu-id="3a6a4-111">Описание</span><span class="sxs-lookup"><span data-stu-id="3a6a4-111">Description</span></span>|  
|-------------|-----------------|  
|[\<applicationPool>](applicationpool-element-web-settings.md)|<span data-ttu-id="3a6a4-112">Задает параметры конфигурации для пулов приложений IIS в файле aspnet. config.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-112">Specifies configuration settings for IIS application pools in an aspnet.config file.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3a6a4-113">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3a6a4-113">Parent Elements</span></span>  
  
|<span data-ttu-id="3a6a4-114">Элемент</span><span class="sxs-lookup"><span data-stu-id="3a6a4-114">Element</span></span>|<span data-ttu-id="3a6a4-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3a6a4-115">Description</span></span>|  
|-------------|-----------------|  
|[\<configuration>](../configuration-element.md)|<span data-ttu-id="3a6a4-116">Указывает корневой элемент в каждом файле конфигурации, который используется средой CLR и .NET Framework приложениями.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-116">Specifies the root element in every configuration file that is used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a6a4-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="3a6a4-117">Remarks</span></span>  

<span data-ttu-id="3a6a4-118">`system.web`Элемент и его дочерний `applicationPool` элемент были добавлены в .NET Framework в .NET Framework 3,5 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="3a6a4-118">The `system.web` element and its child `applicationPool` element were added to the .NET Framework as of .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="3a6a4-119">При запуске IIS 7,0 или более поздних версий в интегрированном режиме эта комбинация элементов позволяет настроить, как ASP.NET управляет потоками и как она помещает запросы в очередь, когда ASP.NET размещается в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-119">When you run IIS 7.0 or later versions in Integrated mode, this element combination lets you configure how ASP.NET manages threads and how it queues requests when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="3a6a4-120">При запуске IIS 7,0 или более поздних версий в классическом или режиме ISAPI эти параметры игнорируются.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-120">If you run IIS 7.0 or later versions in Classic or ISAPI mode, these settings are ignored.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3a6a4-121">Пример</span><span class="sxs-lookup"><span data-stu-id="3a6a4-121">Example</span></span>  

<span data-ttu-id="3a6a4-122">В следующем примере показано, как настроить поведение ASP.NET на уровне процесса в файле aspnet. config, если ASP.NET размещается в пуле приложений IIS.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-122">The following example shows how to configure ASP.NET process-wide behavior in the aspnet.config file when ASP.NET is hosted in an IIS application pool.</span></span> <span data-ttu-id="3a6a4-123">В примере предполагается, что службы IIS работают в режиме интеграции и что приложение использует .NET Framework 3,5 с пакетом обновления 1 (SP1) или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-123">The example assumes that IIS is running in Integrated mode and that the application is using the .NET Framework 3.5 SP1 or a later version.</span></span> <span data-ttu-id="3a6a4-124">Такое поведение не происходит в версиях .NET Framework более ранних, чем .NET Framework 3,5 с пакетом обновления 1 (SP1).</span><span class="sxs-lookup"><span data-stu-id="3a6a4-124">This behavior does not occur in versions of the .NET Framework earlier than the .NET Framework 3.5 SP1.</span></span> <span data-ttu-id="3a6a4-125">Значения в примере являются значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3a6a4-125">The values in the example are the default values.</span></span>  
  
```xml  
<configuration>  
  <system.web>  
    <applicationPool
        maxConcurrentRequestsPerCPU="5000"
        maxConcurrentThreadsPerCPU="0"
        requestQueueLimit="5000" />  
  </system.web>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="3a6a4-126">Сведения об элементе</span><span class="sxs-lookup"><span data-stu-id="3a6a4-126">Element Information</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a6a4-127">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="3a6a4-127">Namespace</span></span>||  
|<span data-ttu-id="3a6a4-128">Имя схемы</span><span class="sxs-lookup"><span data-stu-id="3a6a4-128">Schema Name</span></span>||  
|<span data-ttu-id="3a6a4-129">Файл проверки</span><span class="sxs-lookup"><span data-stu-id="3a6a4-129">Validation File</span></span>||  
|<span data-ttu-id="3a6a4-130">Может быть пустым</span><span class="sxs-lookup"><span data-stu-id="3a6a4-130">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="3a6a4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="3a6a4-131">See also</span></span>

- [<span data-ttu-id="3a6a4-132">\<applicationPool>Элемент (веб-параметры)</span><span class="sxs-lookup"><span data-stu-id="3a6a4-132">\<applicationPool> Element (Web Settings)</span></span>](applicationpool-element-web-settings.md)
