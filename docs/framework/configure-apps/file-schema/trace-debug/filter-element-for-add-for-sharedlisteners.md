---
title: <filter>Элемент для <add> для<sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: 6fb52cdfa5792ab6059b60d8dbb91c107cd666ca
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153457"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="4158c-102">\<filter>Элемент для \<add> для\<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="4158c-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="4158c-103">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="4158c-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="4158c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4158c-104">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4158c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4158c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4158c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4158c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4158c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4158c-107">Attributes</span></span>  
  
|<span data-ttu-id="4158c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4158c-108">Attribute</span></span>|<span data-ttu-id="4158c-109">Описание</span><span class="sxs-lookup"><span data-stu-id="4158c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4158c-110">**type**</span><span class="sxs-lookup"><span data-stu-id="4158c-110">**type**</span></span>|<span data-ttu-id="4158c-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4158c-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="4158c-112">Указывает тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="4158c-112">Specifies the type of the filter.</span></span> <span data-ttu-id="4158c-113">Можно использовать только полное имя типа (в формате <xref:System.Type.FullName%2A?displayProperty=nameWithType> Свойства) или можно использовать полное имя типа, включая сведения о сборке (в формате <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> Свойства).</span><span class="sxs-lookup"><span data-stu-id="4158c-113">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="4158c-114">Сведения о создании полного имени типа см. в разделе [Указание полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="4158c-114">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="4158c-115">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="4158c-115">**initializeData**</span></span>|<span data-ttu-id="4158c-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4158c-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4158c-117">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="4158c-117">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4158c-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4158c-118">Child Elements</span></span>  
 <span data-ttu-id="4158c-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="4158c-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4158c-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4158c-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4158c-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="4158c-121">Element</span></span>|<span data-ttu-id="4158c-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4158c-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4158c-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4158c-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4158c-124">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="4158c-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="4158c-125">Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="4158c-125">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="4158c-126">Добавляет прослушиватель в коллекцию **шаредлистенерс** .</span><span class="sxs-lookup"><span data-stu-id="4158c-126">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4158c-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="4158c-127">Remarks</span></span>  
 <span data-ttu-id="4158c-128">Если прослушиватель определен в элементе элемента `<add>` `<sharedListeners>` , то фильтр для этого прослушивателя должен быть определен в `<filter>` элементе, который является дочерним по отношению к `<add>` элементу.</span><span class="sxs-lookup"><span data-stu-id="4158c-128">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="4158c-129">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4158c-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4158c-130">Пример</span><span class="sxs-lookup"><span data-stu-id="4158c-130">Example</span></span>  
 <span data-ttu-id="4158c-131">В следующем примере показано, как использовать `<filter>` элемент для добавления фильтра в прослушиватель трассировки `console` в `sharedListeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="4158c-131">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4158c-132">См. также</span><span class="sxs-lookup"><span data-stu-id="4158c-132">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="4158c-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="4158c-133">Trace and Debug Settings Schema</span></span>](index.md)
