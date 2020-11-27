---
title: Событие ExceptionThrown_V1 (трассировка событий Windows)
description: Просмотр подробных сведений о событии трассировки событий Windows ExceptionThrown_V1. Такие данные событий, как имена полей, типы данных и описания, предоставляются для вызываемых исключений.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: c1ba994b291bd278a95e34beb0b02ed6581786e8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263481"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="94d23-104">Событие ExceptionThrown_V1 (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="94d23-104">Exception Thrown_V1 ETW Event</span></span>

<span data-ttu-id="94d23-105">Это событие захватывает информацию о вызванных исключениях.</span><span class="sxs-lookup"><span data-stu-id="94d23-105">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="94d23-106">В следующей таблице показаны ключевое слово, в котором вызывается событие, и уровень события.</span><span class="sxs-lookup"><span data-stu-id="94d23-106">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="94d23-107">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="94d23-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="94d23-108">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="94d23-108">Keyword for raising the event</span></span>|<span data-ttu-id="94d23-109">Level</span><span class="sxs-lookup"><span data-stu-id="94d23-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="94d23-110">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="94d23-110">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="94d23-111">Предупреждение (2)</span><span class="sxs-lookup"><span data-stu-id="94d23-111">Warning (2)</span></span>|  
  
 <span data-ttu-id="94d23-112">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="94d23-112">The following table shows event information.</span></span>  
  
|<span data-ttu-id="94d23-113">Событие</span><span class="sxs-lookup"><span data-stu-id="94d23-113">Event</span></span>|<span data-ttu-id="94d23-114">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="94d23-114">Event ID</span></span>|<span data-ttu-id="94d23-115">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="94d23-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="94d23-116">80</span><span class="sxs-lookup"><span data-stu-id="94d23-116">80</span></span>|<span data-ttu-id="94d23-117">Возникло управляемое исключение.</span><span class="sxs-lookup"><span data-stu-id="94d23-117">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="94d23-118">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="94d23-118">The following table shows event data.</span></span>  
  
|<span data-ttu-id="94d23-119">Имя поля</span><span class="sxs-lookup"><span data-stu-id="94d23-119">Field name</span></span>|<span data-ttu-id="94d23-120">Тип данных</span><span class="sxs-lookup"><span data-stu-id="94d23-120">Data type</span></span>|<span data-ttu-id="94d23-121">Описание</span><span class="sxs-lookup"><span data-stu-id="94d23-121">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="94d23-122">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="94d23-122">Exception Type</span></span>|<span data-ttu-id="94d23-123">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="94d23-123">win:UnicodeString</span></span>|<span data-ttu-id="94d23-124">Тип исключения, например `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="94d23-124">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="94d23-125">Сообщение об исключении</span><span class="sxs-lookup"><span data-stu-id="94d23-125">Exception Message</span></span>|<span data-ttu-id="94d23-126">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="94d23-126">win:UnicodeString</span></span>|<span data-ttu-id="94d23-127">Фактическое сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="94d23-127">Actual exception message.</span></span>|  
|<span data-ttu-id="94d23-128">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="94d23-128">EIPCodeThrow</span></span>|<span data-ttu-id="94d23-129">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="94d23-129">win:Pointer</span></span>|<span data-ttu-id="94d23-130">Указатель на инструкцию, в которой возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="94d23-130">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="94d23-131">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="94d23-131">ExceptionHR</span></span>|<span data-ttu-id="94d23-132">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="94d23-132">win:UInt32</span></span>|<span data-ttu-id="94d23-133">Исключение [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="94d23-133">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="94d23-134">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="94d23-134">ExceptionFlags</span></span>|<span data-ttu-id="94d23-135">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="94d23-135">win:UInt16</span></span>|<span data-ttu-id="94d23-136">0x01: HasInnerException (см. раздел [События трассировки событий Windows в среде CLR](clr-etw-events.md) в документации по Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="94d23-136">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="94d23-137">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="94d23-137">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="94d23-138">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="94d23-138">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="94d23-139">0x08: Искорруптедстатиксцептион (указывает, что состояние процесса повреждено; см. раздел [обработка исключений поврежденного состояния](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="94d23-139">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="94d23-140">0x10: IsCLSCompliant (исключение, производное от <xref:System.Exception>, является CLS-совместимым; в противном случае такое исключение не является CLS-совместимым).</span><span class="sxs-lookup"><span data-stu-id="94d23-140">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="94d23-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="94d23-141">ClrInstanceID</span></span>|<span data-ttu-id="94d23-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="94d23-142">win:UInt16</span></span>|<span data-ttu-id="94d23-143">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="94d23-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94d23-144">См. также</span><span class="sxs-lookup"><span data-stu-id="94d23-144">See also</span></span>

- [<span data-ttu-id="94d23-145">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="94d23-145">CLR ETW Events</span></span>](clr-etw-events.md)
