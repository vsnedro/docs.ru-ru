---
title: <remove> Элемент для <listeners> для <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 01b797e1fb62d32e9f0d44c54b803dd969615361
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173839"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="a5027-102">\<remove> Элемент для \<listeners> для \<trace></span><span class="sxs-lookup"><span data-stu-id="a5027-102">\<remove> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="a5027-103">Удаляет прослушиватель из коллекции **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="a5027-103">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="a5027-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5027-104">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5027-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="a5027-105">Attributes and Elements</span></span>  

 <span data-ttu-id="a5027-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="a5027-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5027-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="a5027-107">Attributes</span></span>  
  
|<span data-ttu-id="a5027-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="a5027-108">Attribute</span></span>|<span data-ttu-id="a5027-109">Описание</span><span class="sxs-lookup"><span data-stu-id="a5027-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5027-110">**name**</span><span class="sxs-lookup"><span data-stu-id="a5027-110">**name**</span></span>|<span data-ttu-id="a5027-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="a5027-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="a5027-112">Имя прослушивателя, удаляемого из коллекции **прослушивателей** .</span><span class="sxs-lookup"><span data-stu-id="a5027-112">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5027-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="a5027-113">Child Elements</span></span>  

 <span data-ttu-id="a5027-114">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="a5027-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5027-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="a5027-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a5027-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="a5027-116">Element</span></span>|<span data-ttu-id="a5027-117">Описание</span><span class="sxs-lookup"><span data-stu-id="a5027-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a5027-118">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5027-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="a5027-119">Указывает прослушиватель, который собирает, хранит и маршрутизирует сообщения.</span><span class="sxs-lookup"><span data-stu-id="a5027-119">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="a5027-120">Прослушиватели направляют выходные данные трассировки в соответствующий целевой объект.</span><span class="sxs-lookup"><span data-stu-id="a5027-120">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a5027-121">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="a5027-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="a5027-122">Настройка службы трассировки ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="a5027-122">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5027-123">Remarks</span><span class="sxs-lookup"><span data-stu-id="a5027-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a5027-124">При удалении <xref:System.Diagnostics.DefaultTraceListener> из `Listeners` коллекции изменяется поведение <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> методов,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> и <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="a5027-124">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="a5027-125">Вызов `Assert` метода или `Fail` обычно приводит к отображению окна сообщения, однако окно сообщения не отображается, если объект <xref:System.Diagnostics.DefaultTraceListener> отсутствует в `Listeners` коллекции.</span><span class="sxs-lookup"><span data-stu-id="a5027-125">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5027-126">Пример</span><span class="sxs-lookup"><span data-stu-id="a5027-126">Example</span></span>  

 <span data-ttu-id="a5027-127">В следующем примере показано, как удалить прослушиватель трассировки по умолчанию из коллекции **прослушивателей** трассировки.</span><span class="sxs-lookup"><span data-stu-id="a5027-127">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5027-128">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a5027-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="a5027-129">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="a5027-129">Trace and Debug Settings Schema</span></span>](index.md)
