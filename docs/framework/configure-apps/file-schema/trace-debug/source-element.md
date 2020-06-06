---
title: Элемент <source>
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153299"
---
# <a name="source-element"></a><span data-ttu-id="4bf0f-102">Элемент \<source></span><span class="sxs-lookup"><span data-stu-id="4bf0f-102">\<source> Element</span></span>
<span data-ttu-id="4bf0f-103">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-103">Specifies a trace source that initiates tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a><span data-ttu-id="4bf0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4bf0f-104">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bf0f-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="4bf0f-105">Attributes and Elements</span></span>  
 <span data-ttu-id="4bf0f-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bf0f-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="4bf0f-107">Attributes</span></span>  
  
|<span data-ttu-id="4bf0f-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="4bf0f-108">Attribute</span></span>|<span data-ttu-id="4bf0f-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="4bf0f-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="4bf0f-110">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4bf0f-111">Задает имя источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-111">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="4bf0f-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4bf0f-113">Задает имя экземпляра переключателя трассировки в приложении.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-113">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="4bf0f-114">Если параметр не определен в `<switches>` элементе, значение указывает уровень для переключателя.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-114">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="4bf0f-115">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4bf0f-116">Указывает тип переключателя трассировки.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-116">Specifies the type of the trace switch.</span></span> <span data-ttu-id="4bf0f-117">При наличии тип должен быть допустимым именем класса и не может быть пустой строкой.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-117">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="4bf0f-118">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4bf0f-119">Задает значение для атрибута, зависящего от источника трассировки, определяемого <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> методом для этого источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-119">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4bf0f-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="4bf0f-120">Child Elements</span></span>  
  
|<span data-ttu-id="4bf0f-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="4bf0f-121">Element</span></span>|<span data-ttu-id="4bf0f-122">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf0f-122">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="4bf0f-123">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-123">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4bf0f-124">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="4bf0f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4bf0f-125">Элемент</span><span class="sxs-lookup"><span data-stu-id="4bf0f-125">Element</span></span>|<span data-ttu-id="4bf0f-126">Описание</span><span class="sxs-lookup"><span data-stu-id="4bf0f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4bf0f-127">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4bf0f-128">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4bf0f-129">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-129">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bf0f-130">Примечания</span><span class="sxs-lookup"><span data-stu-id="4bf0f-130">Remarks</span></span>  
 <span data-ttu-id="4bf0f-131">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bf0f-132">Пример</span><span class="sxs-lookup"><span data-stu-id="4bf0f-132">Example</span></span>  
 <span data-ttu-id="4bf0f-133">В следующем примере показано, как с помощью `<source>` элемента добавить источник трассировки `mySource` и задать уровень для коммутатора источника с именем `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="4bf0f-133">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="4bf0f-134">Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="4bf0f-134">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
        <switches>  
           <add name="sourceSwitch" value="Warning" />  
        </switches>
  </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4bf0f-135">См. также</span><span class="sxs-lookup"><span data-stu-id="4bf0f-135">See also</span></span>

- [<span data-ttu-id="4bf0f-136">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="4bf0f-136">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="4bf0f-137">Переключатели трассировки</span><span class="sxs-lookup"><span data-stu-id="4bf0f-137">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
