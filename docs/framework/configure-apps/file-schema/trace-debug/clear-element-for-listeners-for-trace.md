---
title: <clear>Элемент для <listeners> для<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153546"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="a99ef-102">\<clear>Элемент для \<listeners> для\<trace></span><span class="sxs-lookup"><span data-stu-id="a99ef-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="a99ef-103">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="a99ef-103">Clears the `Listeners` collection for trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="a99ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a99ef-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a99ef-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a99ef-105">Attributes and Elements</span></span>  
 <span data-ttu-id="a99ef-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a99ef-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a99ef-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a99ef-107">Attributes</span></span>  
 <span data-ttu-id="a99ef-108">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a99ef-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a99ef-109">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a99ef-109">Child Elements</span></span>  
 <span data-ttu-id="a99ef-110">Нет.</span><span class="sxs-lookup"><span data-stu-id="a99ef-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a99ef-111">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a99ef-111">Parent Elements</span></span>  
  
|<span data-ttu-id="a99ef-112">Элемент</span><span class="sxs-lookup"><span data-stu-id="a99ef-112">Element</span></span>|<span data-ttu-id="a99ef-113">Описание</span><span class="sxs-lookup"><span data-stu-id="a99ef-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a99ef-114">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a99ef-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a99ef-115">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a99ef-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="a99ef-116">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="a99ef-116">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="a99ef-117">Содержит прослушиватели, собирающие, сохраняющие и направляющие сообщения.</span><span class="sxs-lookup"><span data-stu-id="a99ef-117">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="a99ef-118">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="a99ef-118">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a99ef-119">Примечания</span><span class="sxs-lookup"><span data-stu-id="a99ef-119">Remarks</span></span>  
 <span data-ttu-id="a99ef-120">`<clear>`Элемент удаляет все прослушиватели из `Listeners` коллекции для трассировки.</span><span class="sxs-lookup"><span data-stu-id="a99ef-120">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="a99ef-121">Элемент можно использовать `<clear>` перед использованием `<add>` элемента, чтобы убедиться в отсутствии других активных прослушивателей в коллекции.</span><span class="sxs-lookup"><span data-stu-id="a99ef-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="a99ef-122">Можно очистить `Listeners` коллекцию программным путем, вызвав <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> метод для <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> Свойства ( `System.Diagnostics.Trace.Listeners.Clear()` ).</span><span class="sxs-lookup"><span data-stu-id="a99ef-122">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="a99ef-123">Этот элемент можно использовать в файле конфигурации компьютера (Machine. config) и в файле конфигурации приложения.</span><span class="sxs-lookup"><span data-stu-id="a99ef-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a99ef-124">`<clear>`Элемент удаляет <xref:System.Diagnostics.DefaultTraceListener> из `Listeners` коллекции, изменяя поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> методов,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a99ef-124">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="a99ef-125">Вызов `Assert` метода или `Fail` обычно приводит к отображению окна сообщения.</span><span class="sxs-lookup"><span data-stu-id="a99ef-125">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="a99ef-126">Однако окно сообщения не отображается, если объект <xref:System.Diagnostics.DefaultTraceListener> отсутствует в `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="a99ef-126">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a99ef-127">Пример</span><span class="sxs-lookup"><span data-stu-id="a99ef-127">Example</span></span>  
 <span data-ttu-id="a99ef-128">В следующем примере показано, как использовать `<clear>` элемент перед использованием `<add>` элемента для добавления прослушивателя `console` в `Listeners` коллекцию для трассировки.</span><span class="sxs-lookup"><span data-stu-id="a99ef-128">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="a99ef-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a99ef-129">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="a99ef-130">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="a99ef-130">Trace and Debug Settings Schema</span></span>](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="a99ef-131">Прослушиватели трассировки</span><span class="sxs-lookup"><span data-stu-id="a99ef-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
