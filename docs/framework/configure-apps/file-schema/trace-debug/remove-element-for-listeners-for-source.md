---
title: <remove>Элемент для <listeners> для<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 657e6db2af9b99b3bbf03afc6aab02c58a830f2d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153339"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="e1f18-102">\<remove>Элемент для \<listeners> для\<source></span><span class="sxs-lookup"><span data-stu-id="e1f18-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="e1f18-103">Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1f18-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="e1f18-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1f18-104">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e1f18-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="e1f18-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e1f18-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="e1f18-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e1f18-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="e1f18-107">Attributes</span></span>  
  
|<span data-ttu-id="e1f18-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="e1f18-108">Attribute</span></span>|<span data-ttu-id="e1f18-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e1f18-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="e1f18-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="e1f18-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="e1f18-111">Имя прослушивателя, который необходимо удалить из `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="e1f18-111">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e1f18-112">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="e1f18-112">Child Elements</span></span>  
 <span data-ttu-id="e1f18-113">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="e1f18-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e1f18-114">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="e1f18-114">Parent Elements</span></span>  
  
|<span data-ttu-id="e1f18-115">Элемент</span><span class="sxs-lookup"><span data-stu-id="e1f18-115">Element</span></span>|<span data-ttu-id="e1f18-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e1f18-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e1f18-117">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e1f18-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e1f18-118">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1f18-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="e1f18-119">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1f18-119">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="e1f18-120">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1f18-120">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e1f18-121">Указывает прослушиватели, собирающие, хранящие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="e1f18-121">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1f18-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="e1f18-122">Remarks</span></span>  
 <span data-ttu-id="e1f18-123">`<remove>`Элемент удаляет указанный прослушиватель из `Listeners` коллекции для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="e1f18-123">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="e1f18-124">Можно удалить элемент из `Listeners` коллекции для источника трассировки программным путем, вызвав <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> метод для <xref:System.Diagnostics.TraceSource.Listeners%2A> свойства <xref:System.Diagnostics.TraceSource> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="e1f18-124">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="e1f18-125">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="e1f18-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e1f18-126">Пример</span><span class="sxs-lookup"><span data-stu-id="e1f18-126">Example</span></span>  
 <span data-ttu-id="e1f18-127">В следующем примере показано, как использовать `<remove>` элемент перед использованием элемента, `<add>` чтобы добавить прослушиватель `console` в `Listeners` коллекцию для источника трассировки `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="e1f18-127">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="e1f18-128">См. также</span><span class="sxs-lookup"><span data-stu-id="e1f18-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="e1f18-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="e1f18-129">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="e1f18-130">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="e1f18-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
