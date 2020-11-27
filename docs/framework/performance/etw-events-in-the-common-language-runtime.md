---
title: События в среде CLR (трассировка событий Windows)
description: Чтение сводки и просмотр ссылок на события трассировки событий Windows (ETW) в среде CLR.
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: 5bb9b6a2-7b57-4aea-8809-32b28bc73e88
ms.openlocfilehash: ab9cb7c53171ebf1dd0d48dec133464fe4042043
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263636"
---
# <a name="etw-events-in-the-common-language-runtime"></a><span data-ttu-id="dd992-103">События в среде CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="dd992-103">ETW Events in the Common Language Runtime</span></span>

<span data-ttu-id="dd992-104">В общеязыковой среде выполнения (CLR) реализован полезный механизм трассировки событий (ETW), который позволяет получать диагностические сведения для широкого спектра событий отладки и профилирования.</span><span class="sxs-lookup"><span data-stu-id="dd992-104">The common language runtime (CLR) provides useful event tracing for Windows (ETW) diagnostic information through a large variety of debugging and profiling events.</span></span> <span data-ttu-id="dd992-105">События трассировки событий Windows в среде CLR используют систему трассировки Windows ETW, дополняя существующие средства профилирования и отладки, реализованные в общеязыковой среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="dd992-105">CLR ETW events leverage the Windows ETW tracing system to augment the existing profiling and debugging support provided by the common language runtime.</span></span>  
  
 <span data-ttu-id="dd992-106">Дополнительные сведения о трассировке событий Windows доступны в статье [улучшение отладки и настройки производительности с помощью ETW](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) .</span><span class="sxs-lookup"><span data-stu-id="dd992-106">More information about ETW is available in the [Improve Debugging and Performance Tuning with ETW](/archive/msdn-magazine/2007/april/event-tracing-improve-debugging-and-performance-tuning-with-etw) article.</span></span> <span data-ttu-id="dd992-107">Сведения о программе Xperf можно найти в записи [Windows Performance Toolkit — Xperf](/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) блога NTDebugging.</span><span class="sxs-lookup"><span data-stu-id="dd992-107">Information about Xperf can be found in the entry [Windows Performance Toolkit - Xperf](/archive/blogs/ntdebugging/windows-performance-toolkit-xperf) in the NTDebugging blog.</span></span>  
  
 <span data-ttu-id="dd992-108">Для всех событий, описанных в разделах о событиях, требуется .NET Framework 4 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="dd992-108">The .NET Framework 4 or later is required for all the events described in the event topics.</span></span> <span data-ttu-id="dd992-109">Минимальный поддерживаемый клиент — операционная система Windows Vista; минимальный поддерживаемый сервер — Windows Server 2008.</span><span class="sxs-lookup"><span data-stu-id="dd992-109">The Windows Vista operating system is the minimum supported client, and Windows Server 2008 is the minimum supported server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd992-110">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="dd992-110">In This Section</span></span>  

 [<span data-ttu-id="dd992-111">Контроль ведения журнала .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dd992-111">Controlling .NET Framework Logging</span></span>](controlling-logging.md)  
 <span data-ttu-id="dd992-112">Описывает средства и команды для захвата и просмотра событий трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="dd992-112">Describes the tools and commands for capturing and viewing ETW events.</span></span>  
  
 [<span data-ttu-id="dd992-113">Поставщики ETW среды CLR</span><span class="sxs-lookup"><span data-stu-id="dd992-113">CLR ETW Providers</span></span>](clr-etw-providers.md)  
 <span data-ttu-id="dd992-114">Содержит сведения о поставщиках среды выполнения и очистки, а также о том, как использовать их для сбора данных трассировки событий Windows.</span><span class="sxs-lookup"><span data-stu-id="dd992-114">Provides information about the runtime and rundown providers, and how you can use them for ETW data collection.</span></span>  
  
 [<span data-ttu-id="dd992-115">Ключевые слова и уровни среды CLR (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="dd992-115">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)  
 <span data-ttu-id="dd992-116">Описывает ключевые слова для поставщиков среды выполнения и очистки, которые обеспечивают фильтрацию событий по категориям.</span><span class="sxs-lookup"><span data-stu-id="dd992-116">Describes the keywords for the Runtime and Rundown providers that enable the filtering of events by category.</span></span>  
  
 [<span data-ttu-id="dd992-117">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="dd992-117">CLR ETW Events</span></span>](clr-etw-events.md)  
 <span data-ttu-id="dd992-118">Содержит подробные сведения о событиях трассировки событий Windows в среде CLR, а также соответствующих ключевых словах, уровнях и данных событий.</span><span class="sxs-lookup"><span data-stu-id="dd992-118">Provides detailed information about CLR ETW events, their keywords, levels, and event data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd992-119">См. также</span><span class="sxs-lookup"><span data-stu-id="dd992-119">See also</span></span>

- [<span data-ttu-id="dd992-120">ETW Events in the .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dd992-120">ETW Events in the .NET Framework</span></span>](etw-events.md)
