---
title: Элемент <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: 617b42a0be2be272a78b33be997cce632d1c6dcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198929"
---
# <a name="trace-element"></a><span data-ttu-id="8a820-102">Элемент \<trace></span><span class="sxs-lookup"><span data-stu-id="8a820-102">\<trace> Element</span></span>

<span data-ttu-id="8a820-103">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="8a820-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a><span data-ttu-id="8a820-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8a820-104">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8a820-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8a820-105">Attributes and Elements</span></span>  

 <span data-ttu-id="8a820-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8a820-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8a820-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8a820-107">Attributes</span></span>  
  
|<span data-ttu-id="8a820-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8a820-108">Attribute</span></span>|<span data-ttu-id="8a820-109">Описание</span><span class="sxs-lookup"><span data-stu-id="8a820-109">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="8a820-110">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8a820-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8a820-111">Указывает, будут ли прослушиватели трассировки автоматически сбрасывать выходной буфер после каждой операции записи.</span><span class="sxs-lookup"><span data-stu-id="8a820-111">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="8a820-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8a820-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8a820-113">Задает количество пробелов для отступа.</span><span class="sxs-lookup"><span data-stu-id="8a820-113">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="8a820-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="8a820-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="8a820-115">Указывает, следует ли использовать глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="8a820-115">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="8a820-116">Атрибут автозаписи</span><span class="sxs-lookup"><span data-stu-id="8a820-116">autoflush Attribute</span></span>  
  
|<span data-ttu-id="8a820-117">Значение</span><span class="sxs-lookup"><span data-stu-id="8a820-117">Value</span></span>|<span data-ttu-id="8a820-118">Описание</span><span class="sxs-lookup"><span data-stu-id="8a820-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8a820-119">Не очищает выходной буфер автоматически.</span><span class="sxs-lookup"><span data-stu-id="8a820-119">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="8a820-120">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8a820-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="8a820-121">Автоматически очищает выходной буфер.</span><span class="sxs-lookup"><span data-stu-id="8a820-121">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="8a820-122">Атрибут useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="8a820-122">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="8a820-123">Значение</span><span class="sxs-lookup"><span data-stu-id="8a820-123">Value</span></span>|<span data-ttu-id="8a820-124">Описание</span><span class="sxs-lookup"><span data-stu-id="8a820-124">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="8a820-125">Не использует глобальную блокировку, если прослушиватель является потокобезопасным; в противном случае использует глобальную блокировку.</span><span class="sxs-lookup"><span data-stu-id="8a820-125">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="8a820-126">Использует глобальную блокировку независимо от того, является ли прослушиватель потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="8a820-126">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="8a820-127">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8a820-127">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8a820-128">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8a820-128">Child Elements</span></span>  
  
|<span data-ttu-id="8a820-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a820-129">Element</span></span>|<span data-ttu-id="8a820-130">Описание</span><span class="sxs-lookup"><span data-stu-id="8a820-130">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="8a820-131">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="8a820-131">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8a820-132">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8a820-132">Parent Elements</span></span>  
  
|<span data-ttu-id="8a820-133">Элемент</span><span class="sxs-lookup"><span data-stu-id="8a820-133">Element</span></span>|<span data-ttu-id="8a820-134">Описание</span><span class="sxs-lookup"><span data-stu-id="8a820-134">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="8a820-135">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8a820-135">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="8a820-136">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="8a820-136">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8a820-137">Пример</span><span class="sxs-lookup"><span data-stu-id="8a820-137">Example</span></span>  

 <span data-ttu-id="8a820-138">В следующем примере показано, как использовать `<trace>` элемент для добавления прослушивателя `MyListener` в `Listeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="8a820-138">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="8a820-139">`MyListener` создает файл с именем `MyListener.log` и записывает выходные данные в файл.</span><span class="sxs-lookup"><span data-stu-id="8a820-139">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="8a820-140">`useGlobalLock`Атрибут имеет значение `false` , что приводит к тому, что глобальная блокировка не будет использоваться, если прослушиватель трассировки является потокобезопасным.</span><span class="sxs-lookup"><span data-stu-id="8a820-140">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="8a820-141">`autoflush`Атрибут имеет значение `true` , что приводит к тому, что прослушиватель трассировки выполняет запись в файл независимо от того, <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> вызывается ли метод.</span><span class="sxs-lookup"><span data-stu-id="8a820-141">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="8a820-142">Атрибуту присваивается значение `indentsize` 0 (ноль), что приводит к тому, что при вызове метода прослушиватель устанавливает отступы в ноль пробелов <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="8a820-142">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a820-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8a820-143">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="8a820-144">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="8a820-144">Trace and Debug Settings Schema</span></span>](index.md)
