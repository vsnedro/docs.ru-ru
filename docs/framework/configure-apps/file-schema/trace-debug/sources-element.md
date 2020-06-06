---
title: Элемент <sources>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153273"
---
# <a name="sources-element"></a><span data-ttu-id="3e903-102">Элемент \<sources></span><span class="sxs-lookup"><span data-stu-id="3e903-102">\<sources> Element</span></span>
<span data-ttu-id="3e903-103">Указывает источники трассировки, инициирующие сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="3e903-103">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="3e903-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e903-104">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3e903-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="3e903-105">Attributes and Elements</span></span>  
 <span data-ttu-id="3e903-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="3e903-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3e903-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="3e903-107">Attributes</span></span>  
 <span data-ttu-id="3e903-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="3e903-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3e903-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="3e903-109">Child Elements</span></span>  
  
|<span data-ttu-id="3e903-110">Элемент</span><span class="sxs-lookup"><span data-stu-id="3e903-110">Element</span></span>|<span data-ttu-id="3e903-111">Описание</span><span class="sxs-lookup"><span data-stu-id="3e903-111">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="3e903-112">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="3e903-112">Required element.</span></span><br /><br /> <span data-ttu-id="3e903-113">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="3e903-113">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3e903-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="3e903-114">Parent Elements</span></span>  
  
|<span data-ttu-id="3e903-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="3e903-115">Element</span></span>|<span data-ttu-id="3e903-116">Описание</span><span class="sxs-lookup"><span data-stu-id="3e903-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3e903-117">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3e903-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3e903-118">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="3e903-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e903-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e903-119">Remarks</span></span>  
 <span data-ttu-id="3e903-120">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="3e903-120">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e903-121">Пример</span><span class="sxs-lookup"><span data-stu-id="3e903-121">Example</span></span>  
 <span data-ttu-id="3e903-122">В следующем примере показано, как с помощью `<sources>` элемента добавить источник трассировки `mySource` и задать уровень для коммутатора источника с именем `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="3e903-122">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="3e903-123">Добавляется прослушиватель трассировки консоли, который записывает данные трассировки на консоль.</span><span class="sxs-lookup"><span data-stu-id="3e903-123">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
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
         <add name="sourceSwitch" value="Warning" />  
      </switches>
   </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3e903-124">См. также</span><span class="sxs-lookup"><span data-stu-id="3e903-124">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="3e903-125">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="3e903-125">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
