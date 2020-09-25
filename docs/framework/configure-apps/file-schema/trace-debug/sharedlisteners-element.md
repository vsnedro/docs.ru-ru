---
title: Элемент <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 7e249e59423740b36e42f59fae8854412d01a0cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173852"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="20f44-102">Элемент \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="20f44-102">\<sharedListeners> Element</span></span>

<span data-ttu-id="20f44-103">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="20f44-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="20f44-104">По умолчанию эти прослушиватели не получают никаких трассировок, поэтому невозможно получить эти прослушиватели во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="20f44-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="20f44-105">Прослушиватели, идентифицированные как общие прослушиватели, можно добавлять в источники или трассировки по имени.</span><span class="sxs-lookup"><span data-stu-id="20f44-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="20f44-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20f44-106">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20f44-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="20f44-107">Attributes and Elements</span></span>  

 <span data-ttu-id="20f44-108">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="20f44-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20f44-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="20f44-109">Attributes</span></span>  

 <span data-ttu-id="20f44-110">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="20f44-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="20f44-111">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="20f44-111">Child Elements</span></span>  
  
|<span data-ttu-id="20f44-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="20f44-112">Element</span></span>|<span data-ttu-id="20f44-113">Описание</span><span class="sxs-lookup"><span data-stu-id="20f44-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="20f44-114">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="20f44-114">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="20f44-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="20f44-115">Parent Elements</span></span>  
  
|<span data-ttu-id="20f44-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="20f44-116">Element</span></span>|<span data-ttu-id="20f44-117">Описание</span><span class="sxs-lookup"><span data-stu-id="20f44-117">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="20f44-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="20f44-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="20f44-119">Задает корневой элемент для раздела конфигурации ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="20f44-119">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20f44-120">Remarks</span><span class="sxs-lookup"><span data-stu-id="20f44-120">Remarks</span></span>  

 <span data-ttu-id="20f44-121">Добавление прослушивателя в коллекцию общих прослушивателей не сделает его активным прослушивателем.</span><span class="sxs-lookup"><span data-stu-id="20f44-121">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="20f44-122">Он по-прежнему должен быть добавлен в источник трассировки или в трассировку путем добавления в `Listeners` коллекцию для этого элемента Trace.</span><span class="sxs-lookup"><span data-stu-id="20f44-122">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="20f44-123">Классы прослушивателей в .NET Framework являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="20f44-123">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="20f44-124">Этот элемент можно использовать в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="20f44-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20f44-125">Пример</span><span class="sxs-lookup"><span data-stu-id="20f44-125">Example</span></span>  

 <span data-ttu-id="20f44-126">В следующем примере показано, как использовать `<sharedListeners>` элемент для добавления прослушивателя `console` в `Listeners` коллекцию для <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> классов и.</span><span class="sxs-lookup"><span data-stu-id="20f44-126">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="20f44-127">Прослушиватель трассировки консоли записывает данные трассировки в консоль с помощью вызовов либо к, либо к <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> .</span><span class="sxs-lookup"><span data-stu-id="20f44-127">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="20f44-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="20f44-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="20f44-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="20f44-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="20f44-130">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="20f44-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
