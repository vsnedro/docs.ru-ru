---
title: Сводка типов трассировок
ms.date: 03/30/2017
ms.assetid: e639410b-d1d1-479c-b78e-a4701d4e4085
ms.openlocfilehash: e8d222d6f093f5db3bd620194bfde7edd4b998a8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96259249"
---
# <a name="trace-type-summary"></a><span data-ttu-id="8bdb3-102">Сводка типов трассировок</span><span class="sxs-lookup"><span data-stu-id="8bdb3-102">Trace Type Summary</span></span>

<span data-ttu-id="8bdb3-103">[Уровни источника](xref:System.Diagnostics.SourceLevels) определяют различные уровни трассировки: критическая, ошибка, предупреждение, информация и подробный, а также описание `ActivityTracing` флага, который переключает выходные данные границ трассировки и событий перемещения действий.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-103">[Source Levels](xref:System.Diagnostics.SourceLevels) defines various trace levels: Critical, Error, Warning, Information, and Verbose, as well as provides a description of the `ActivityTracing` flag, which toggles the output of trace boundary and activity transfer events.</span></span>  
  
 <span data-ttu-id="8bdb3-104">Также можно просматривать <xref:System.Diagnostics.TraceEventType> типы трассировок, которые могут быть выпущены из <xref:System.Diagnostics> .</span><span class="sxs-lookup"><span data-stu-id="8bdb3-104">You can also review <xref:System.Diagnostics.TraceEventType> for the types of traces which can be emitted from <xref:System.Diagnostics>.</span></span>  
  
 <span data-ttu-id="8bdb3-105">В следующей таблице перечислены наиболее важные из них.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-105">The following table lists the most important ones.</span></span>  
  
|<span data-ttu-id="8bdb3-106">Тип трассировки</span><span class="sxs-lookup"><span data-stu-id="8bdb3-106">Trace Type</span></span>|<span data-ttu-id="8bdb3-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8bdb3-107">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="8bdb3-108">Критический</span><span class="sxs-lookup"><span data-stu-id="8bdb3-108">Critical</span></span>|<span data-ttu-id="8bdb3-109">Неустранимая ошибка или сбой в работе приложения.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-109">Fatal error or application crash.</span></span>|  
|<span data-ttu-id="8bdb3-110">Ошибка</span><span class="sxs-lookup"><span data-stu-id="8bdb3-110">Error</span></span>|<span data-ttu-id="8bdb3-111">Устранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-111">Recoverable error.</span></span>|  
|<span data-ttu-id="8bdb3-112">Предупреждение</span><span class="sxs-lookup"><span data-stu-id="8bdb3-112">Warning</span></span>|<span data-ttu-id="8bdb3-113">Информационное сообщение.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-113">Informational message.</span></span>|  
|<span data-ttu-id="8bdb3-114">Сведения</span><span class="sxs-lookup"><span data-stu-id="8bdb3-114">Information</span></span>|<span data-ttu-id="8bdb3-115">Некритическая проблема.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-115">Non-critical problem.</span></span>|  
|<span data-ttu-id="8bdb3-116">Подробный</span><span class="sxs-lookup"><span data-stu-id="8bdb3-116">Verbose</span></span>|<span data-ttu-id="8bdb3-117">Трассировка отладки.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-117">Debugging trace.</span></span>|  
|<span data-ttu-id="8bdb3-118">Начать</span><span class="sxs-lookup"><span data-stu-id="8bdb3-118">Start</span></span>|<span data-ttu-id="8bdb3-119">Начало логического блока обработки.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-119">Starting of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8bdb3-120">Приостановить</span><span class="sxs-lookup"><span data-stu-id="8bdb3-120">Suspend</span></span>|<span data-ttu-id="8bdb3-121">Приостановка логического блока обработки. </span><span class="sxs-lookup"><span data-stu-id="8bdb3-121">Suspension of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8bdb3-122">Возобновить</span><span class="sxs-lookup"><span data-stu-id="8bdb3-122">Resume</span></span>|<span data-ttu-id="8bdb3-123">Возобновление логического блока обработки. </span><span class="sxs-lookup"><span data-stu-id="8bdb3-123">Resumption of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8bdb3-124">Остановить</span><span class="sxs-lookup"><span data-stu-id="8bdb3-124">Stop</span></span>|<span data-ttu-id="8bdb3-125">Остановка логического блока обработки. </span><span class="sxs-lookup"><span data-stu-id="8bdb3-125">Stopping of a logical unit of processing.</span></span>|  
|<span data-ttu-id="8bdb3-126">Перенос</span><span class="sxs-lookup"><span data-stu-id="8bdb3-126">Transfer</span></span>|<span data-ttu-id="8bdb3-127">Изменение идентификации взаимосвязей.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-127">Changing of correlation identity.</span></span>|  
  
 <span data-ttu-id="8bdb3-128">Действие определяется как сочетание перечисленных выше типов трассировок.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-128">An activity is defined as a combination of the trace types above.</span></span>  
  
 <span data-ttu-id="8bdb3-129">Ниже приведено регулярное выражение, определяющее идеальное действие в локальной области (области источника трассировки):</span><span class="sxs-lookup"><span data-stu-id="8bdb3-129">The following is a regular expression that defines an ideal activity in a local (trace source) scope,</span></span>  
  
 `R = Start (Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop`  
  
 <span data-ttu-id="8bdb3-130">Это означает, что действие должно удовлетворять следующим условиям.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-130">This means that an activity must satisfy the following conditions.</span></span>  
  
- <span data-ttu-id="8bdb3-131">Должно запускаться и останавливаться трассировками Start и Stop соответственно.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-131">It must start and stop respectively by a Start and Stop traces</span></span>  
  
- <span data-ttu-id="8bdb3-132">Трассировка Transfer должна непосредственно предшествовать трассировке Suspend или Resume.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-132">It must have a Transfer trace immediately preceding a Suspend or Resume trace</span></span>  
  
- <span data-ttu-id="8bdb3-133">Не должно содержать никаких трассировок между трассировками Suspend и Resume, если такие трассировки имеются.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-133">It must not have any traces between the Suspend and Resume traces if such traces exist</span></span>  
  
- <span data-ttu-id="8bdb3-134">Может содержать любые и в любом количестве трассировки уровня Critical/Error/Warning/Information/Verbose/Transfer при условии соблюдения предыдущих условий.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-134">It can have any and as many of critical/Error/Warning/Information/Verbose/Transfer traces as long as the previous conditions are observed</span></span>  
  
 <span data-ttu-id="8bdb3-135">Ниже приведено регулярное выражение, определяющее идеальное действие в глобальной области,</span><span class="sxs-lookup"><span data-stu-id="8bdb3-135">The following is a regular expression that defines an ideal activity in the global scope,</span></span>  
  
`R+`  
  
 <span data-ttu-id="8bdb3-136">где R - регулярное выражение для действия в локальной области.</span><span class="sxs-lookup"><span data-stu-id="8bdb3-136">with R being the regular expression for an activity in the local scope.</span></span> <span data-ttu-id="8bdb3-137">Таким образом, получаем:</span><span class="sxs-lookup"><span data-stu-id="8bdb3-137">This translates to,</span></span>  
  
`[R+ = Start ( Critical | Error | Warning | Information | Verbose | Transfer | (Transfer Suspend Transfer Resume) )* Stop]+`
