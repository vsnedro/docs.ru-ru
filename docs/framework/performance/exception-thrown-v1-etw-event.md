---
title: Событие ExceptionThrown_V1 (трассировка событий Windows)
description: Просмотр подробных сведений о событии трассировки событий Windows ExceptionThrown_V1. Такие данные событий, как имена полей, типы данных и описания, предоставляются для вызываемых исключений.
ms.date: 03/30/2017
helpviewer_keywords:
- ExceptionThrown_V1 event [.NET Framework]
- ETW, ExceptionThrown_V1 event (CLR)
ms.assetid: 0d3da389-6b7b-40f6-a877-fac546d6019c
ms.openlocfilehash: f4ae277b5dfb09d2676755fec2208b63906ead84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554675"
---
# <a name="exception-thrown_v1-etw-event"></a><span data-ttu-id="9f8a5-104">Событие ExceptionThrown_V1 (трассировка событий Windows)</span><span class="sxs-lookup"><span data-stu-id="9f8a5-104">Exception Thrown_V1 ETW Event</span></span>
<span data-ttu-id="9f8a5-105">Это событие захватывает информацию о вызванных исключениях.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-105">This event captures information about the exceptions that are thrown.</span></span>  
  
 <span data-ttu-id="9f8a5-106">В следующей таблице показаны ключевое слово, в котором вызывается событие, и уровень события.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-106">The following table shows the keyword under which the event is raised, and the level of the event.</span></span> <span data-ttu-id="9f8a5-107">(Дополнительные сведения см. в разделе [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span><span class="sxs-lookup"><span data-stu-id="9f8a5-107">(For more information, see [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="9f8a5-108">Ключевое слово для вызова события</span><span class="sxs-lookup"><span data-stu-id="9f8a5-108">Keyword for raising the event</span></span>|<span data-ttu-id="9f8a5-109">Level</span><span class="sxs-lookup"><span data-stu-id="9f8a5-109">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="9f8a5-110">`ExceptionKeyword` (0x8000)</span><span class="sxs-lookup"><span data-stu-id="9f8a5-110">`ExceptionKeyword` (0x8000)</span></span>|<span data-ttu-id="9f8a5-111">Предупреждение (2)</span><span class="sxs-lookup"><span data-stu-id="9f8a5-111">Warning (2)</span></span>|  
  
 <span data-ttu-id="9f8a5-112">В таблице ниже представлены сведения о событии.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-112">The following table shows event information.</span></span>  
  
|<span data-ttu-id="9f8a5-113">Событие</span><span class="sxs-lookup"><span data-stu-id="9f8a5-113">Event</span></span>|<span data-ttu-id="9f8a5-114">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="9f8a5-114">Event ID</span></span>|<span data-ttu-id="9f8a5-115">Условие вызова</span><span class="sxs-lookup"><span data-stu-id="9f8a5-115">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ExceptionThrown_V1`|<span data-ttu-id="9f8a5-116">80</span><span class="sxs-lookup"><span data-stu-id="9f8a5-116">80</span></span>|<span data-ttu-id="9f8a5-117">Возникло управляемое исключение.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-117">A managed exception is thrown.</span></span>|  
  
 <span data-ttu-id="9f8a5-118">В таблице ниже представлены данные события.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-118">The following table shows event data.</span></span>  
  
|<span data-ttu-id="9f8a5-119">Имя поля</span><span class="sxs-lookup"><span data-stu-id="9f8a5-119">Field name</span></span>|<span data-ttu-id="9f8a5-120">Тип данных</span><span class="sxs-lookup"><span data-stu-id="9f8a5-120">Data type</span></span>|<span data-ttu-id="9f8a5-121">Описание</span><span class="sxs-lookup"><span data-stu-id="9f8a5-121">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="9f8a5-122">Тип исключения</span><span class="sxs-lookup"><span data-stu-id="9f8a5-122">Exception Type</span></span>|<span data-ttu-id="9f8a5-123">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9f8a5-123">win:UnicodeString</span></span>|<span data-ttu-id="9f8a5-124">Тип исключения, например `System.NullReferenceException`.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-124">Type of the exception; for example, `System.NullReferenceException`.</span></span>|  
|<span data-ttu-id="9f8a5-125">Сообщение об исключении</span><span class="sxs-lookup"><span data-stu-id="9f8a5-125">Exception Message</span></span>|<span data-ttu-id="9f8a5-126">win:UnicodeString</span><span class="sxs-lookup"><span data-stu-id="9f8a5-126">win:UnicodeString</span></span>|<span data-ttu-id="9f8a5-127">Фактическое сообщение об исключении.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-127">Actual exception message.</span></span>|  
|<span data-ttu-id="9f8a5-128">EIPCodeThrow</span><span class="sxs-lookup"><span data-stu-id="9f8a5-128">EIPCodeThrow</span></span>|<span data-ttu-id="9f8a5-129">win:Pointer</span><span class="sxs-lookup"><span data-stu-id="9f8a5-129">win:Pointer</span></span>|<span data-ttu-id="9f8a5-130">Указатель на инструкцию, в которой возникло исключение.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-130">Instruction pointer where exception occurred.</span></span>|  
|<span data-ttu-id="9f8a5-131">ExceptionHR</span><span class="sxs-lookup"><span data-stu-id="9f8a5-131">ExceptionHR</span></span>|<span data-ttu-id="9f8a5-132">win:UInt32</span><span class="sxs-lookup"><span data-stu-id="9f8a5-132">win:UInt32</span></span>|<span data-ttu-id="9f8a5-133">Исключение [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span><span class="sxs-lookup"><span data-stu-id="9f8a5-133">Exception [HRESULT](/openspecs/windows_protocols/ms-erref/0642cb2f-2075-4469-918c-4441e69c548a).</span></span>|  
|<span data-ttu-id="9f8a5-134">ExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="9f8a5-134">ExceptionFlags</span></span>|<span data-ttu-id="9f8a5-135">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9f8a5-135">win:UInt16</span></span>|<span data-ttu-id="9f8a5-136">0x01: HasInnerException (см. раздел [События трассировки событий Windows в среде CLR](clr-etw-events.md) в документации по Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="9f8a5-136">0x01: HasInnerException (see [CLR ETW Events](clr-etw-events.md) in the Visual Basic documentation).</span></span><br /><br /> <span data-ttu-id="9f8a5-137">0x02: IsNestedException.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-137">0x02: IsNestedException.</span></span><br /><br /> <span data-ttu-id="9f8a5-138">0x04: IsRethrownException.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-138">0x04: IsRethrownException.</span></span><br /><br /> <span data-ttu-id="9f8a5-139">0x08: Искорруптедстатиксцептион (указывает, что состояние процесса повреждено; см. раздел [обработка исключений поврежденного состояния](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span><span class="sxs-lookup"><span data-stu-id="9f8a5-139">0x08: IsCorruptedStateException (indicates that the process state is corrupt; see [Handling Corrupted State Exceptions](/archive/msdn-magazine/2009/february/clr-inside-out-handling-corrupted-state-exceptions)).</span></span><br /><br /> <span data-ttu-id="9f8a5-140">0x10: IsCLSCompliant (исключение, производное от <xref:System.Exception>, является CLS-совместимым; в противном случае такое исключение не является CLS-совместимым).</span><span class="sxs-lookup"><span data-stu-id="9f8a5-140">0x10: IsCLSCompliant (an exception that derives from <xref:System.Exception> is CLS-compliant; otherwise, it is not CLS-compliant).</span></span>|  
|<span data-ttu-id="9f8a5-141">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="9f8a5-141">ClrInstanceID</span></span>|<span data-ttu-id="9f8a5-142">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="9f8a5-142">win:UInt16</span></span>|<span data-ttu-id="9f8a5-143">Уникальный идентификатор экземпляра CLR или CoreCLR.</span><span class="sxs-lookup"><span data-stu-id="9f8a5-143">Unique ID for the instance of CLR or CoreCLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9f8a5-144">См. также</span><span class="sxs-lookup"><span data-stu-id="9f8a5-144">See also</span></span>

- [<span data-ttu-id="9f8a5-145">События трассировки событий Windows в среде CLR</span><span class="sxs-lookup"><span data-stu-id="9f8a5-145">CLR ETW Events</span></span>](clr-etw-events.md)
