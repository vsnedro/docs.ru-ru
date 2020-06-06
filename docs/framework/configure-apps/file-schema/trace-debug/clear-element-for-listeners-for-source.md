---
title: <clear>Элемент для <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153585"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="9a0f1-102">\<clear>Элемент для \<listeners> для\<source></span><span class="sxs-lookup"><span data-stu-id="9a0f1-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="9a0f1-103">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-103">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="9a0f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a0f1-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a0f1-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9a0f1-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9a0f1-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a0f1-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9a0f1-107">Attributes</span></span>  
 <span data-ttu-id="9a0f1-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a0f1-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9a0f1-109">Child Elements</span></span>  
 <span data-ttu-id="9a0f1-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9a0f1-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9a0f1-111">Parent Elements</span></span>  
  
|<span data-ttu-id="9a0f1-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="9a0f1-112">Element</span></span>|<span data-ttu-id="9a0f1-113">Описание</span><span class="sxs-lookup"><span data-stu-id="9a0f1-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9a0f1-114">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9a0f1-115">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="9a0f1-116">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-116">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="9a0f1-117">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-117">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="9a0f1-118">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-118">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a0f1-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="9a0f1-119">Remarks</span></span>  
 <span data-ttu-id="9a0f1-120">`<clear>`Элемент удаляет все прослушиватели из `Listeners` коллекции для источника трассировки, включая <xref:System.Diagnostics.DefaultTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="9a0f1-120">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="9a0f1-121">Элемент можно использовать `<clear>` перед использованием `<add>` элемента, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="9a0f1-122">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="9a0f1-122">Configuration File</span></span>  
 <span data-ttu-id="9a0f1-123">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="9a0f1-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9a0f1-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9a0f1-124">Example</span></span>  
 <span data-ttu-id="9a0f1-125">В следующем примере показано, как использовать `<clear>` элемент перед использованием `<add>` элементов для добавления прослушивателей `console` и `textListener` в `Listeners` коллекцию для источника трассировки `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="9a0f1-125">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
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
  
## <a name="see-also"></a><span data-ttu-id="9a0f1-126">См. также</span><span class="sxs-lookup"><span data-stu-id="9a0f1-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="9a0f1-127">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="9a0f1-127">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9a0f1-128">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="9a0f1-128">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
