---
title: Элемент <add> для <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153611"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="e9fb2-102">Элемент \<add> для \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="e9fb2-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="e9fb2-103">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="e9fb2-104">`sharedListeners`— Это коллекция прослушивателей, [\<source>](source-element.md) на которые [\<trace>](trace-element.md) могут ссылаться любые или.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="e9fb2-105">По умолчанию прослушиватели в `sharedListeners` коллекции не помещаются в `Listeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="e9fb2-106">Они должны быть добавлены по имени в [\<source>](source-element.md) или [\<trace>](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="e9fb2-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="e9fb2-107">Невозможно получить прослушиватели в `sharedListeners` коллекции в коде во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="e9fb2-108">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9fb2-108">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9fb2-109">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e9fb2-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9fb2-110">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9fb2-111">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e9fb2-111">Attributes</span></span>  
  
|<span data-ttu-id="e9fb2-112">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e9fb2-112">Attribute</span></span>|<span data-ttu-id="e9fb2-113">Описание</span><span class="sxs-lookup"><span data-stu-id="e9fb2-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e9fb2-114">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9fb2-115">Указывает имя прослушивателя, который используется для добавления общего прослушивателя в `Listeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-115">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="e9fb2-116">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="e9fb2-117">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-117">Specifies the type of the listener.</span></span> <span data-ttu-id="e9fb2-118">Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e9fb2-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="e9fb2-119">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e9fb2-120">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-120">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="e9fb2-121">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-121">Optional attribute.</span></span><br/><br/><span data-ttu-id="e9fb2-122">Строковое представление одного или нескольких <xref:System.Diagnostics.TraceOptions> элементов перечисления, которое указывает данные, записываемые в выходные данные трассировки.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-122">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="e9fb2-123">Несколько элементов разделяются запятыми.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-123">Multiple items are separated by commas.</span></span> <span data-ttu-id="e9fb2-124">Значение по умолчанию — None.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-124">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="e9fb2-125">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e9fb2-125">Child Elements</span></span>  
  
|<span data-ttu-id="e9fb2-126">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9fb2-126">Element</span></span>|<span data-ttu-id="e9fb2-127">Описание</span><span class="sxs-lookup"><span data-stu-id="e9fb2-127">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="e9fb2-128">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-128">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9fb2-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e9fb2-129">Parent Elements</span></span>  
  
|<span data-ttu-id="e9fb2-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="e9fb2-130">Element</span></span>|<span data-ttu-id="e9fb2-131">Описание</span><span class="sxs-lookup"><span data-stu-id="e9fb2-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9fb2-132">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e9fb2-133">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="e9fb2-134">Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-134">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9fb2-135">Примечания</span><span class="sxs-lookup"><span data-stu-id="e9fb2-135">Remarks</span></span>  
 <span data-ttu-id="e9fb2-136">Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-136">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="e9fb2-137">Значение `name` атрибута используется для добавления общего прослушивателя в `Listeners` коллекцию либо для трассировки, либо для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-137">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="e9fb2-138">Значение `initializeData` атрибута зависит от типа создаваемого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-138">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="e9fb2-139">Не все прослушиватели трассировки нуждаются в указании `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="e9fb2-139">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9fb2-140">При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен".</span><span class="sxs-lookup"><span data-stu-id="e9fb2-140">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="e9fb2-141">Это предупреждение возникает из-за того, что параметры конфигурации проверяются по абстрактному базовому классу <xref:System.Diagnostics.TraceListener> , который не распознает `initializeData` атрибут.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-141">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="e9fb2-142">Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-142">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="e9fb2-143">В следующей таблице показаны прослушиватели трассировки, которые включены в состав .NET Framework и описываются значения их `initializeData` атрибутов.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-143">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="e9fb2-144">Класс прослушивателя трассировки</span><span class="sxs-lookup"><span data-stu-id="e9fb2-144">Trace listener class</span></span>|<span data-ttu-id="e9fb2-145">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="e9fb2-145">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="e9fb2-146">`useErrorStream`Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-146">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="e9fb2-147">Задайте для `initializeData` атрибута значение " `true` ", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок; задайте для него значение " `false` ", чтобы выполнить запись в стандартный выходной поток.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-147">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="e9fb2-148">Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-148">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9fb2-149">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-149">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9fb2-150">Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-150">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9fb2-151">Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-151">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="e9fb2-152">Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-152">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="e9fb2-153">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="e9fb2-153">Configuration File</span></span>  
 <span data-ttu-id="e9fb2-154">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-154">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9fb2-155">Пример</span><span class="sxs-lookup"><span data-stu-id="e9fb2-155">Example</span></span>  
 <span data-ttu-id="e9fb2-156">В следующем примере показано, как использовать `<add>` элементы для добавления в <xref:System.Diagnostics.TextWriterTraceListener> `textListener` `sharedListeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-156">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="e9fb2-157">`textListener`добавляется по имени в `Listeners` коллекцию для источника трассировки `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="e9fb2-157">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="e9fb2-158">`textListener`Прослушиватель записывает выходные данные трассировки в файл myListener. log.</span><span class="sxs-lookup"><span data-stu-id="e9fb2-158">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"
        type="System.Diagnostics.TextWriterTraceListener"
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="e9fb2-159">См. также</span><span class="sxs-lookup"><span data-stu-id="e9fb2-159">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e9fb2-160">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="e9fb2-160">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9fb2-161">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="e9fb2-161">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
