---
title: <filter>Элемент для <add> для <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 0cb668782de263d5f784691f46cb8b74541d942b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153520"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="9e304-102">\<filter>Элемент для \<add> для \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="9e304-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="9e304-103">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="9e304-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="9e304-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e304-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e304-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9e304-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9e304-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9e304-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e304-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9e304-107">Attributes</span></span>  
  
|<span data-ttu-id="9e304-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9e304-108">Attribute</span></span>|<span data-ttu-id="9e304-109">Описание</span><span class="sxs-lookup"><span data-stu-id="9e304-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="9e304-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9e304-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="9e304-111">Указывает тип фильтра, который должен наследоваться от <xref:System.Diagnostics.TraceFilter> класса.</span><span class="sxs-lookup"><span data-stu-id="9e304-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="9e304-112">Можно использовать имя, уточненное пространством имен типа, которое соответствует <xref:System.Type.FullName%2A> свойству типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие <xref:System.Type.AssemblyQualifiedName%2A> свойству.</span><span class="sxs-lookup"><span data-stu-id="9e304-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="9e304-113">Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="9e304-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="9e304-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="9e304-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="9e304-115">Строка, передаваемая конструктору для указанного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="9e304-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9e304-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9e304-116">Child Elements</span></span>  
 <span data-ttu-id="9e304-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9e304-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9e304-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9e304-118">Parent Elements</span></span>  
  
|<span data-ttu-id="9e304-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="9e304-119">Element</span></span>|<span data-ttu-id="9e304-120">Описание</span><span class="sxs-lookup"><span data-stu-id="9e304-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9e304-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9e304-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9e304-122">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="9e304-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="9e304-123">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="9e304-123">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="9e304-124">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="9e304-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="9e304-125">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="9e304-125">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="9e304-126">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="9e304-126">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="9e304-127">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="9e304-127">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e304-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e304-128">Remarks</span></span>  
 <span data-ttu-id="9e304-129">`<filter>`Элемент должен содержаться в `<add>` элементе для прослушивателя источника трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="9e304-129">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="9e304-130">Если прослушиватель определен в [\<sharedListeners>](sharedlisteners-element.md) , то фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="9e304-130">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="9e304-131">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9e304-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9e304-132">Пример</span><span class="sxs-lookup"><span data-stu-id="9e304-132">Example</span></span>  
 <span data-ttu-id="9e304-133">В следующем примере показано, как с помощью `<filter>` элемента добавить фильтр в прослушиватель `console` в `Listeners` коллекции для источника трассировки `myTraceSource` , указав уровень событий фильтра как `Error` .</span><span class="sxs-lookup"><span data-stu-id="9e304-133">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e304-134">См. также</span><span class="sxs-lookup"><span data-stu-id="9e304-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="9e304-135">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="9e304-135">Trace and Debug Settings Schema</span></span>](index.md)
