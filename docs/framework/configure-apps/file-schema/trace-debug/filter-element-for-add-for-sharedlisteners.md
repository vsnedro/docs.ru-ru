---
title: <filter> Элемент для <add> для <sharedListeners>
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
ms.openlocfilehash: e140148a342e31d6ade7def8849d8a7738301704
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173930"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="386cc-102">\<filter> Элемент для \<add> для \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="386cc-102">\<filter> Element for \<add> for \<sharedListeners></span></span>

<span data-ttu-id="386cc-103">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="386cc-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="386cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="386cc-104">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="386cc-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="386cc-105">Attributes and Elements</span></span>  

 <span data-ttu-id="386cc-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="386cc-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="386cc-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="386cc-107">Attributes</span></span>  
  
|<span data-ttu-id="386cc-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="386cc-108">Attribute</span></span>|<span data-ttu-id="386cc-109">Описание</span><span class="sxs-lookup"><span data-stu-id="386cc-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="386cc-110">**type**</span><span class="sxs-lookup"><span data-stu-id="386cc-110">**type**</span></span>|<span data-ttu-id="386cc-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="386cc-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="386cc-112">Указывает тип фильтра.</span><span class="sxs-lookup"><span data-stu-id="386cc-112">Specifies the type of the filter.</span></span> <span data-ttu-id="386cc-113">Можно использовать только полное имя типа (в формате <xref:System.Type.FullName%2A?displayProperty=nameWithType> Свойства) или можно использовать полное имя типа, включая сведения о сборке (в формате <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> Свойства).</span><span class="sxs-lookup"><span data-stu-id="386cc-113">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="386cc-114">Сведения о создании полного имени типа см. в разделе [Указание полных имен типов](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="386cc-114">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="386cc-115">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="386cc-115">**initializeData**</span></span>|<span data-ttu-id="386cc-116">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="386cc-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="386cc-117">Строка, передаваемая конструктору для указанного класса.</span><span class="sxs-lookup"><span data-stu-id="386cc-117">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="386cc-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="386cc-118">Child Elements</span></span>  

 <span data-ttu-id="386cc-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="386cc-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="386cc-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="386cc-120">Parent Elements</span></span>  
  
|<span data-ttu-id="386cc-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="386cc-121">Element</span></span>|<span data-ttu-id="386cc-122">Описание</span><span class="sxs-lookup"><span data-stu-id="386cc-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="386cc-123">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="386cc-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="386cc-124">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="386cc-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="386cc-125">Коллекция прослушивателей, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="386cc-125">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="386cc-126">Добавляет прослушиватель в коллекцию **шаредлистенерс** .</span><span class="sxs-lookup"><span data-stu-id="386cc-126">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="386cc-127">Remarks</span><span class="sxs-lookup"><span data-stu-id="386cc-127">Remarks</span></span>  

 <span data-ttu-id="386cc-128">Если прослушиватель определен в элементе элемента `<add>` `<sharedListeners>` , то фильтр для этого прослушивателя должен быть определен в `<filter>` элементе, который является дочерним по отношению к `<add>` элементу.</span><span class="sxs-lookup"><span data-stu-id="386cc-128">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="386cc-129">Этот элемент можно использовать в файле конфигурации компьютера (Machine.config) и файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="386cc-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="386cc-130">Пример</span><span class="sxs-lookup"><span data-stu-id="386cc-130">Example</span></span>  

 <span data-ttu-id="386cc-131">В следующем примере показано, как использовать `<filter>` элемент для добавления фильтра в прослушиватель трассировки `console` в `sharedListeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="386cc-131">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="386cc-132">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="386cc-132">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="386cc-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="386cc-133">Trace and Debug Settings Schema</span></span>](index.md)
