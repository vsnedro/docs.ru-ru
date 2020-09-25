---
title: Схема параметров трассировки и отладки
ms.date: 03/30/2017
helpviewer_keywords:
- tracing [.NET Framework], trace and debug settings schema
- configuration schema [.NET Framework], trace and debug settings
- configuration settings [.NET Framework], tracing
- schema configuration settings
- configuration settings [.NET Framework], debugging
- trace listeners, trace and debug settings schema
- configuration sections [.NET Framework]
- elements [.NET Framework], trace and debug settings
ms.assetid: 277ca5f6-e1c4-41b6-a47f-3a67ce5b94ac
ms.openlocfilehash: ae089e941d75df7ba1cd87b5b92a514a33bfbf85
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195198"
---
# <a name="trace-and-debug-settings-schema"></a><span data-ttu-id="ca246-102">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="ca246-102">Trace and Debug Settings Schema</span></span>

<span data-ttu-id="ca246-103">Параметры трассировки и отладки определяют прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-103">Trace and debug settings specify trace listeners that collect, store, and route messages, and the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="ca246-104">В приведенной ниже таблице описывается назначение каждого элемента параметров трассировки и отладки.</span><span class="sxs-lookup"><span data-stu-id="ca246-104">The following table describes the function of each trace and debug settings element.</span></span>  
  
|<span data-ttu-id="ca246-105">Элемент</span><span class="sxs-lookup"><span data-stu-id="ca246-105">Element</span></span>|<span data-ttu-id="ca246-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ca246-106">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="ca246-107">Добавляет прослушиватель в коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-107">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="ca246-108">Добавляет прослушиватель в коллекцию `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="ca246-108">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<add>](add-element-for-sharedlisteners.md)|<span data-ttu-id="ca246-109">Добавляет прослушиватель в коллекцию `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ca246-109">Adds a listener to the `sharedListeners` collection.</span></span>|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="ca246-110">Задает уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-110">Specifies the level where a trace switch is set.</span></span>|  
|[\<assert>](assert-element.md)|<span data-ttu-id="ca246-111">Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="ca246-111">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="ca246-112">Очищает коллекцию `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-112">Clears the `Listeners` collection for a trace source.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="ca246-113">Очищает коллекцию `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-113">Clears the `Listeners` collection for trace.</span></span>|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="ca246-114">Добавляет фильтр к прослушивателю в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-114">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="ca246-115">Добавляет фильтр к прослушивателю в коллекции `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-115">Adds a filter to a listener in the `Listeners` collection for trace.</span></span>|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="ca246-116">Добавляет фильтр к прослушивателю в коллекции `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ca246-116">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="ca246-117">Определяет прослушиватели в коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-117">Specifies listeners for the `Listeners` collection for a trace source.</span></span>|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="ca246-118">Определяет прослушиватели в коллекции `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-118">Specifies listeners for the `Listeners` collection for trace.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="ca246-119">Задает размер глобальной памяти, совместно используемой счетчиками производительности.</span><span class="sxs-lookup"><span data-stu-id="ca246-119">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="ca246-120">Удаляет прослушиватель из коллекции `Listeners` для трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-120">Removes a listener from the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="ca246-121">Удаляет прослушиватель из коллекции `Listeners` для источника трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-121">Removes a listener from the `Listeners` collection for a trace source.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="ca246-122">Содержит прослушиватели, на которые может ссылаться любой источник или элемент трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-122">Contains listeners that any source or trace element can reference.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="ca246-123">Содержит источники трассировки, которые инициируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-123">Contains trace sources that initiate tracing messages.</span></span>|  
|[\<source>](source-element.md)|<span data-ttu-id="ca246-124">Содержит источник трассировки, который инициирует сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="ca246-125">Содержит ключи трассировки и уровень, на котором они установлены.</span><span class="sxs-lookup"><span data-stu-id="ca246-125">Contains trace switches and the level where the trace switches are set.</span></span>|  
|[\<system.diagnostics>](system-diagnostics-element.md)|<span data-ttu-id="ca246-126">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="ca246-127">Содержит прослушиватели, которые собирают, хранят и маршрутизируют сообщения трассировки.</span><span class="sxs-lookup"><span data-stu-id="ca246-127">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca246-128">См. также</span><span class="sxs-lookup"><span data-stu-id="ca246-128">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="ca246-129">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="ca246-129">Configuration File Schema</span></span>](../index.md)
