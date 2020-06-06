---
title: Элемент <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153416"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="ec925-102">Элемент \<listeners> для \<source></span><span class="sxs-lookup"><span data-stu-id="ec925-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="ec925-103">Добавляет или удаляет прослушиватели в <xref:System.Diagnostics.TraceSource.Listeners%2A> коллекции для <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="ec925-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="ec925-104">Прослушиватель направляет выходные данные трассировки в соответствующий целевой объект, например журнал, окно или текстовый файл.</span><span class="sxs-lookup"><span data-stu-id="ec925-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**  
  
## <a name="syntax"></a><span data-ttu-id="ec925-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ec925-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ec925-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ec925-106">Attributes and Elements</span></span>  
 <span data-ttu-id="ec925-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ec925-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ec925-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ec925-108">Attributes</span></span>  
 <span data-ttu-id="ec925-109">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="ec925-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="ec925-110">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ec925-110">Child Elements</span></span>  
  
|<span data-ttu-id="ec925-111">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec925-111">Element</span></span>|<span data-ttu-id="ec925-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ec925-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="ec925-113">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="ec925-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="ec925-114">Удаляет прослушиватель из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="ec925-114">Removes a listener from the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="ec925-115">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="ec925-115">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ec925-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ec925-116">Parent Elements</span></span>  
  
|<span data-ttu-id="ec925-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="ec925-117">Element</span></span>|<span data-ttu-id="ec925-118">Описание</span><span class="sxs-lookup"><span data-stu-id="ec925-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ec925-119">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ec925-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ec925-120">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ec925-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="ec925-121">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ec925-121">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="ec925-122">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ec925-122">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec925-123">Примечания</span><span class="sxs-lookup"><span data-stu-id="ec925-123">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="ec925-124">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="ec925-124">Configuration File</span></span>  
 <span data-ttu-id="ec925-125">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="ec925-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec925-126">Пример</span><span class="sxs-lookup"><span data-stu-id="ec925-126">Example</span></span>  
 <span data-ttu-id="ec925-127">В следующем примере показано, как использовать `<listeners>` элемент для добавления прослушивателя трассировки консоли в `mySource` источник и для удаления прослушивателя трассировки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ec925-127">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ec925-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ec925-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="ec925-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="ec925-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ec925-130">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="ec925-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
