---
title: <filter>Элемент для <add> для <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153470"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="44203-102">\<filter>Элемент для \<add> для \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="44203-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="44203-103">Добавляет фильтр в прослушиватель в `Listeners` коллекции для трассировки.</span><span class="sxs-lookup"><span data-stu-id="44203-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="44203-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44203-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44203-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44203-105">Attributes and Elements</span></span>  
 <span data-ttu-id="44203-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="44203-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44203-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44203-107">Attributes</span></span>  
  
|<span data-ttu-id="44203-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="44203-108">Attribute</span></span>|<span data-ttu-id="44203-109">Описание</span><span class="sxs-lookup"><span data-stu-id="44203-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="44203-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="44203-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="44203-111">Указывает тип фильтра, который должен наследоваться от <xref:System.Diagnostics.TraceFilter> класса.</span><span class="sxs-lookup"><span data-stu-id="44203-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="44203-112">Можно использовать имя, уточненное пространством имен типа, которое соответствует <xref:System.Type.FullName%2A> свойству типа, или можно использовать полное имя типа, включая сведения о сборке, соответствующие <xref:System.Type.AssemblyQualifiedName%2A> свойству.</span><span class="sxs-lookup"><span data-stu-id="44203-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="44203-113">Дополнительные сведения о полных именах типов см. в разделе Указание полных [имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="44203-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="44203-114">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="44203-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="44203-115">Строка, передаваемая конструктору для указанного класса фильтра.</span><span class="sxs-lookup"><span data-stu-id="44203-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44203-116">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44203-116">Child Elements</span></span>  
 <span data-ttu-id="44203-117">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="44203-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44203-118">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44203-118">Parent Elements</span></span>  
  
|<span data-ttu-id="44203-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="44203-119">Element</span></span>|<span data-ttu-id="44203-120">Описание</span><span class="sxs-lookup"><span data-stu-id="44203-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44203-121">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44203-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="44203-122">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="44203-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="44203-123">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="44203-123">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="44203-124">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="44203-124">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="44203-125">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="44203-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="44203-126">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="44203-126">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44203-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="44203-127">Remarks</span></span>  
 <span data-ttu-id="44203-128">`<filter>`Элемент должен содержаться в `<add>` элементе для прослушивателя трассировки, который указывает тип прослушивателя, а не только имя прослушивателя, определенного в [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="44203-128">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="44203-129">Если прослушиватель определен в [\<sharedListeners>](sharedlisteners-element.md) , то фильтр для этого прослушивателя должен быть определен в этом элементе.</span><span class="sxs-lookup"><span data-stu-id="44203-129">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="44203-130">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="44203-130">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44203-131">Пример</span><span class="sxs-lookup"><span data-stu-id="44203-131">Example</span></span>  
 <span data-ttu-id="44203-132">В следующем примере показано, как с помощью `<filter>` элемента добавить фильтр в прослушиватель `console` в `Listeners` коллекции для трассировки, указав уровень события фильтра в качестве `Error` .</span><span class="sxs-lookup"><span data-stu-id="44203-132">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44203-133">См. также</span><span class="sxs-lookup"><span data-stu-id="44203-133">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="44203-134">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="44203-134">Trace and Debug Settings Schema</span></span>](index.md)
