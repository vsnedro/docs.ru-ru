---
title: <System. Diagnostics> элемент
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: aff324ac9952c95c78d7ca15572651dba23b79b7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195172"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="62951-102">Элемент \<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="62951-102">\<system.diagnostics> Element</span></span>

<span data-ttu-id="62951-103">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="62951-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="62951-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62951-104">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62951-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="62951-105">Attributes and Elements</span></span>  

 <span data-ttu-id="62951-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="62951-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62951-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="62951-107">Attributes</span></span>  

 <span data-ttu-id="62951-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="62951-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="62951-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="62951-109">Child Elements</span></span>  
  
|<span data-ttu-id="62951-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="62951-110">Element</span></span>|<span data-ttu-id="62951-111">Описание</span><span class="sxs-lookup"><span data-stu-id="62951-111">Description</span></span>|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|<span data-ttu-id="62951-112">Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="62951-112">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="62951-113">Задает размер глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="62951-113">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="62951-114">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="62951-114">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="62951-115">Прослушиватели, идентифицированные как общие прослушиватели, можно добавлять в источники или трассировки по имени.</span><span class="sxs-lookup"><span data-stu-id="62951-115">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="62951-116">Указывает источники трассировки, инициирующие сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="62951-116">Specifies trace sources that initiate tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="62951-117">Содержит переключатели трассировки и уровни, на которых заданы переключатели трассировки.</span><span class="sxs-lookup"><span data-stu-id="62951-117">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="62951-118">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="62951-118">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="62951-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="62951-119">Parent Elements</span></span>  
  
|<span data-ttu-id="62951-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="62951-120">Element</span></span>|<span data-ttu-id="62951-121">Описание</span><span class="sxs-lookup"><span data-stu-id="62951-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="62951-122">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="62951-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="62951-123">Пример</span><span class="sxs-lookup"><span data-stu-id="62951-123">Example</span></span>  

 <span data-ttu-id="62951-124">В следующем примере показано, как внедрить переключатель трассировки и прослушиватель трассировки внутри **\<system.diagnostics>** элемента.</span><span class="sxs-lookup"><span data-stu-id="62951-124">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="62951-125">`General`Параметр трассировки имеет значение <xref:System.Diagnostics.TraceLevel> Level.</span><span class="sxs-lookup"><span data-stu-id="62951-125">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="62951-126">Прослушиватель трассировки `myListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="62951-126">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62951-127">В .NET Framework версии 2.0 для указания значения переключателя можно использовать текст.</span><span class="sxs-lookup"><span data-stu-id="62951-127">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="62951-128">Например, можно указать `true` для <xref:System.Diagnostics.BooleanSwitch> или использовать текст, представляющий значение перечисления, например `Error` , для <xref:System.Diagnostics.TraceSwitch> .</span><span class="sxs-lookup"><span data-stu-id="62951-128">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="62951-129">Строка `<add name="myTraceSwitch" value="Error" />` эквивалентна `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="62951-129">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="62951-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="62951-130">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="62951-131">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="62951-131">Trace and Debug Settings Schema</span></span>](index.md)
