---
title: <add> Элемент для <listeners> для <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: a5abaffbad986785b8879297883da9614f0a8103
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201698"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="a6a72-102">\<add> Элемент для \<listeners> для \<source></span><span class="sxs-lookup"><span data-stu-id="a6a72-102">\<add> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="a6a72-103">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="a6a72-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="a6a72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6a72-104">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a6a72-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a6a72-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a6a72-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a6a72-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a6a72-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a6a72-107">Attributes</span></span>  
  
|<span data-ttu-id="a6a72-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a6a72-108">Attribute</span></span>|<span data-ttu-id="a6a72-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a6a72-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="a6a72-110">Обязательный атрибут, если вы не ссылаетесь на прослушиватель в `sharedListeners` коллекции. в этом случае необходимо ссылаться на него по имени (см. [Пример](#example)).</span><span class="sxs-lookup"><span data-stu-id="a6a72-110">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="a6a72-111">Указывает тип прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="a6a72-111">Specifies the type of the listener.</span></span> <span data-ttu-id="a6a72-112">Необходимо использовать строку, которая соответствует требованиям, указанным в указании [полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="a6a72-112">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="a6a72-113">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a6a72-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a6a72-114">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="a6a72-114">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="a6a72-115">Исключение создается, <xref:System.Configuration.ConfigurationException> Если класс не имеет конструктора, принимающего строку.</span><span class="sxs-lookup"><span data-stu-id="a6a72-115">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="a6a72-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a6a72-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a6a72-117">Указывает имя прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="a6a72-117">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="a6a72-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a6a72-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="a6a72-119">Указывает <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> значение свойства для прослушивателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="a6a72-119">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="a6a72-120">[настраиваемые атрибуты]</span><span class="sxs-lookup"><span data-stu-id="a6a72-120">[custom attributes]</span></span>|<span data-ttu-id="a6a72-121">Необязательные атрибуты.</span><span class="sxs-lookup"><span data-stu-id="a6a72-121">Optional attributes.</span></span><br /><br /> <span data-ttu-id="a6a72-122">Задает значение для атрибутов прослушивателя <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> , определенных методом для этого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="a6a72-122">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="a6a72-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> Пример дополнительного атрибута, уникального для <xref:System.Diagnostics.DelimitedListTraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="a6a72-123"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a6a72-124">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a6a72-124">Child Elements</span></span>  
  
|<span data-ttu-id="a6a72-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6a72-125">Element</span></span>|<span data-ttu-id="a6a72-126">Описание</span><span class="sxs-lookup"><span data-stu-id="a6a72-126">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="a6a72-127">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="a6a72-127">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a6a72-128">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a6a72-128">Parent Elements</span></span>  
  
|<span data-ttu-id="a6a72-129">Элемент</span><span class="sxs-lookup"><span data-stu-id="a6a72-129">Element</span></span>|<span data-ttu-id="a6a72-130">Описание</span><span class="sxs-lookup"><span data-stu-id="a6a72-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a6a72-131">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a6a72-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a6a72-132">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a6a72-132">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="a6a72-133">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="a6a72-133">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="a6a72-134">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="a6a72-134">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="a6a72-135">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="a6a72-135">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6a72-136">Remarks</span><span class="sxs-lookup"><span data-stu-id="a6a72-136">Remarks</span></span>  

 <span data-ttu-id="a6a72-137">Классы прослушивателей, поставляемые с .NET Framework, являются производными от <xref:System.Diagnostics.TraceListener> класса.</span><span class="sxs-lookup"><span data-stu-id="a6a72-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="a6a72-138">Если `name` атрибут прослушивателя трассировки не указан, <xref:System.Diagnostics.TraceListener.Name%2A> свойство прослушивателя трассировки по умолчанию имеет пустую строку ("").</span><span class="sxs-lookup"><span data-stu-id="a6a72-138">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="a6a72-139">Если у приложения есть только один прослушиватель, его можно добавить без указания имени, и его можно удалить, указав в качестве имени пустую строку.</span><span class="sxs-lookup"><span data-stu-id="a6a72-139">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="a6a72-140">Однако если приложение имеет несколько прослушивателей, необходимо указать уникальное имя для каждого прослушивателя трассировки, что позволяет определять отдельные прослушиватели трассировки в коллекции и управлять ими <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a6a72-140">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6a72-141">Добавление нескольких прослушивателей трассировки одного и того же типа и с одним и тем же именем приводит к тому, что только один прослушиватель трассировки этого типа и имя добавляются в `Listeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="a6a72-141">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="a6a72-142">Тем не менее можно программно добавить несколько идентичных прослушивателей в `Listeners` коллекцию.</span><span class="sxs-lookup"><span data-stu-id="a6a72-142">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="a6a72-143">Значение `initializeData` атрибута зависит от типа создаваемого прослушивателя.</span><span class="sxs-lookup"><span data-stu-id="a6a72-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="a6a72-144">Не все прослушиватели трассировки нуждаются в указании `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="a6a72-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a6a72-145">При использовании `initializeData` атрибута может появиться предупреждение компилятора "атрибут initializeData не объявлен".</span><span class="sxs-lookup"><span data-stu-id="a6a72-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="a6a72-146">Это предупреждение возникает из-за того, что параметры конфигурации проверяются по абстрактному базовому классу <xref:System.Diagnostics.TraceListener> , который не распознает `initializeData` атрибут.</span><span class="sxs-lookup"><span data-stu-id="a6a72-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="a6a72-147">Как правило, это предупреждение можно игнорировать для реализаций прослушивателя трассировки, имеющих конструктор, принимающий параметр.</span><span class="sxs-lookup"><span data-stu-id="a6a72-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="a6a72-148">В следующей таблице показаны прослушиватели трассировки, которые включены в состав .NET Framework и описываются значения их `initializeData` атрибутов.</span><span class="sxs-lookup"><span data-stu-id="a6a72-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="a6a72-149">Класс прослушивателя трассировки</span><span class="sxs-lookup"><span data-stu-id="a6a72-149">Trace listener class</span></span>|<span data-ttu-id="a6a72-150">значение атрибута initializeData</span><span class="sxs-lookup"><span data-stu-id="a6a72-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a6a72-151">`useErrorStream`Значение для <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> конструктора.</span><span class="sxs-lookup"><span data-stu-id="a6a72-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="a6a72-152">Задайте для `initializeData` атрибута значение " `true` ", чтобы записывать выходные данные трассировки и отладки в стандартный поток ошибок; задайте для него значение " `false` ", чтобы выполнить запись в стандартный выходной поток.</span><span class="sxs-lookup"><span data-stu-id="a6a72-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a6a72-153">Имя файла, в который осуществляет запись объект <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="a6a72-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a6a72-154">Имя существующего источника журнала событий.</span><span class="sxs-lookup"><span data-stu-id="a6a72-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a6a72-155">Имя файла, <xref:System.Diagnostics.EventSchemaTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="a6a72-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a6a72-156">Имя файла, <xref:System.Diagnostics.TextWriterTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="a6a72-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="a6a72-157">Имя файла, <xref:System.Diagnostics.XmlWriterTraceListener> в который производится запись.</span><span class="sxs-lookup"><span data-stu-id="a6a72-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="a6a72-158">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="a6a72-158">Configuration File</span></span>  

 <span data-ttu-id="a6a72-159">Этот элемент можно использовать в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="a6a72-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6a72-160">Пример</span><span class="sxs-lookup"><span data-stu-id="a6a72-160">Example</span></span>  

 <span data-ttu-id="a6a72-161">В следующем примере показано, как использовать `<add>` элементы для добавления прослушивателей `console` и `textListener` в `Listeners` коллекцию для источника трассировки `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="a6a72-161">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="a6a72-162">`textListener`Прослушиватель записывает выходные данные трассировки в файл myListener. log.</span><span class="sxs-lookup"><span data-stu-id="a6a72-162">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a6a72-163">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a6a72-163">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="a6a72-164">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="a6a72-164">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="a6a72-165">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="a6a72-165">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
