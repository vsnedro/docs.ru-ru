---
title: Перечисление CorPinvokeMap
ms.date: 03/30/2017
api_name:
- CorPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPinvokeMap
helpviewer_keywords:
- CorPinvokeMap enumeration [.NET Framework metadata]
ms.assetid: f14f986e-f6ce-42bc-aa23-18150c46d28c
topic_type:
- apiref
ms.openlocfilehash: 199a649b0481c2a740926636345eefbda6831ef2
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007550"
---
# <a name="corpinvokemap-enumeration"></a><span data-ttu-id="0f48f-102">Перечисление CorPinvokeMap</span><span class="sxs-lookup"><span data-stu-id="0f48f-102">CorPinvokeMap Enumeration</span></span>
<span data-ttu-id="0f48f-103">Задает параметры для вызова PInvoke.</span><span class="sxs-lookup"><span data-stu-id="0f48f-103">Specifies options for a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f48f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0f48f-104">Syntax</span></span>  
  
```cpp  
typedef enum  CorPinvokeMap {  
  
    pmNoMangle          = 0x0001,  
  
    pmCharSetMask       = 0x0006,  
    pmCharSetNotSpec    = 0x0000,  
    pmCharSetAnsi       = 0x0002,  
    pmCharSetUnicode    = 0x0004,  
    pmCharSetAuto       = 0x0006,  
  
    pmBestFitUseAssem   = 0x0000,  
    pmBestFitEnabled    = 0x0010,  
    pmBestFitDisabled   = 0x0020,  
    pmBestFitMask       = 0x0030,  
  
    pmThrowOnUnmappableCharUseAssem   = 0x0000,  
    pmThrowOnUnmappableCharEnabled    = 0x1000,  
    pmThrowOnUnmappableCharDisabled   = 0x2000,  
    pmThrowOnUnmappableCharMask       = 0x3000,  
  
    pmSupportsLastError = 0x0040,
  
    pmCallConvMask      = 0x0700,  
    pmCallConvWinapi    = 0x0100,  
    pmCallConvCdecl     = 0x0200,  
    pmCallConvStdcall   = 0x0300,  
    pmCallConvThiscall  = 0x0400,  
    pmCallConvFastcall  = 0x0500,  
  
    pmMaxValue          = 0xFFFF  
  
} CorPinvokeMap;  
```  
  
## <a name="members"></a><span data-ttu-id="0f48f-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0f48f-105">Members</span></span>  
  
|<span data-ttu-id="0f48f-106">Член</span><span class="sxs-lookup"><span data-stu-id="0f48f-106">Member</span></span>|<span data-ttu-id="0f48f-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0f48f-107">Description</span></span>|  
|------------|-----------------|  
|`pmNoMangle`|<span data-ttu-id="0f48f-108">Используйте каждое имя элемента, как указано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-108">Use each member name as specified.</span></span>|  
|`pmCharSetMask`|<span data-ttu-id="0f48f-109">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-109">Reserved.</span></span>|  
|`pmCharSetNotSpec`|<span data-ttu-id="0f48f-110">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-110">Reserved.</span></span>|  
|`pmCharSetAnsi`|<span data-ttu-id="0f48f-111">Маршалирует строки в виде строк многобайтовых символов.</span><span class="sxs-lookup"><span data-stu-id="0f48f-111">Marshal strings as multiple-byte character strings.</span></span>|  
|`pmCharSetUnicode`|<span data-ttu-id="0f48f-112">Маршалирует строки в виде 2-байтных символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="0f48f-112">Marshal strings as Unicode 2-byte characters.</span></span>|  
|`pmCharSetAuto`|<span data-ttu-id="0f48f-113">Выполняет автоматический маршалинг строк способом, соответствующим целевой операционной системе.</span><span class="sxs-lookup"><span data-stu-id="0f48f-113">Automatically marshal strings appropriately for the target operating system.</span></span> <span data-ttu-id="0f48f-114">По умолчанию используется Юникод в Windows NT, Windows 2000, Windows XP и семействе Windows Server 2003. значение по умолчанию — ANSI в Windows 98 и Windows Me.</span><span class="sxs-lookup"><span data-stu-id="0f48f-114">The default is Unicode on Windows NT, Windows 2000, Windows XP, and the Windows Server 2003 family; the default is ANSI on Windows 98 and Windows Me.</span></span>|  
|`pmBestFitUseAssem`|<span data-ttu-id="0f48f-115">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-115">Reserved.</span></span>|  
|`pmBestFitEnabled`|<span data-ttu-id="0f48f-116">Выполните наилучшее сопоставление символов Юникода, не имея точного соответствия в кодировке ANSI.</span><span class="sxs-lookup"><span data-stu-id="0f48f-116">Perform best-fit mapping of Unicode characters that lack an exact match in the ANSI character set.</span></span>|  
|`pmBestFitDisabled`|<span data-ttu-id="0f48f-117">Не выполняйте наилучшее соответствие символов Юникода.</span><span class="sxs-lookup"><span data-stu-id="0f48f-117">Do not perform best-fit mapping of Unicode characters.</span></span> <span data-ttu-id="0f48f-118">В этом случае все несопоставимые символы будут заменены символом "?".</span><span class="sxs-lookup"><span data-stu-id="0f48f-118">In this case, all unmappable characters will be replaced by a ‘?’.</span></span>|  
|`pmBestFitMask`|<span data-ttu-id="0f48f-119">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-119">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharUseAssem`|<span data-ttu-id="0f48f-120">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-120">Reserved.</span></span>|  
|`pmThrowOnUnmappableCharEnabled`|<span data-ttu-id="0f48f-121">Создавать исключение, когда модуль маршалинга взаимодействия встречает несопоставимый символ.</span><span class="sxs-lookup"><span data-stu-id="0f48f-121">Throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharDisabled`|<span data-ttu-id="0f48f-122">Не вызывайте исключение, если модуль маршалинга взаимодействия встречает несопоставимый символ.</span><span class="sxs-lookup"><span data-stu-id="0f48f-122">Do not throw an exception when the interop marshaler encounters an unmappable character.</span></span>|  
|`pmThrowOnUnmappableCharMask`|<span data-ttu-id="0f48f-123">Зарезервированное</span><span class="sxs-lookup"><span data-stu-id="0f48f-123">Reserved</span></span>|  
|`pmSupportsLastError`|<span data-ttu-id="0f48f-124">Разрешить вызываемому `SetLastError` методу вызывать функцию Win32 перед возвратом из метода с атрибутом.</span><span class="sxs-lookup"><span data-stu-id="0f48f-124">Allow the callee to call the Win32 `SetLastError` function before returning from the attributed method.</span></span>|  
|`pmCallConvMask`|<span data-ttu-id="0f48f-125">Зарезервированное</span><span class="sxs-lookup"><span data-stu-id="0f48f-125">Reserved</span></span>|  
|`pmCallConvWinapi`|<span data-ttu-id="0f48f-126">Используйте соглашение о вызовах платформы по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0f48f-126">Use the default platform calling convention.</span></span> <span data-ttu-id="0f48f-127">Например, в Windows значение по умолчанию — `StdCall` и на Windows CE .NET — `Cdecl` .</span><span class="sxs-lookup"><span data-stu-id="0f48f-127">For example, on Windows the default is `StdCall` and on Windows CE .NET it is `Cdecl`.</span></span>|  
|`pmCallConvCdecl`|<span data-ttu-id="0f48f-128">Используйте `Cdecl` соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="0f48f-128">Use the `Cdecl` calling convention.</span></span> <span data-ttu-id="0f48f-129">В этом случае вызывающий объект очищает стек.</span><span class="sxs-lookup"><span data-stu-id="0f48f-129">In this case, the caller cleans the stack.</span></span> <span data-ttu-id="0f48f-130">Это позволяет вызывать функции с `varargs` (то есть функциями, принимающими переменное количество параметров).</span><span class="sxs-lookup"><span data-stu-id="0f48f-130">This enables calling functions with `varargs` (that is, functions that accept a variable number of parameters).</span></span>|  
|`pmCallConvStdcall`|<span data-ttu-id="0f48f-131">Используйте `StdCall` соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="0f48f-131">Use the `StdCall` calling convention.</span></span> <span data-ttu-id="0f48f-132">В этом случае вызываемый объект очищает стек.</span><span class="sxs-lookup"><span data-stu-id="0f48f-132">In this case, the callee cleans the stack.</span></span> <span data-ttu-id="0f48f-133">Это соглашение, используемое по умолчанию для вызова неуправляемых функций с вызовом неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="0f48f-133">This is the default convention for calling unmanaged functions with platform invoke.</span></span>|  
|`pmCallConvThiscall`|<span data-ttu-id="0f48f-134">Используйте `ThisCall` соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="0f48f-134">Use the `ThisCall` calling convention.</span></span> <span data-ttu-id="0f48f-135">В этом случае первый параметр является `this` указателем и хранится в регистре ECX.</span><span class="sxs-lookup"><span data-stu-id="0f48f-135">In this case, the first parameter is the `this` pointer and is stored in register ECX.</span></span> <span data-ttu-id="0f48f-136">Другие параметры помещаются в стек.</span><span class="sxs-lookup"><span data-stu-id="0f48f-136">Other parameters are pushed on the stack.</span></span> <span data-ttu-id="0f48f-137">`ThisCall`Соглашение о вызовах используется для вызова методов для классов, экспортируемых из неуправляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="0f48f-137">The `ThisCall` calling convention is used to call methods on classes exported from an unmanaged DLL.</span></span>|  
|`pmCallConvFastcall`|<span data-ttu-id="0f48f-138">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-138">Reserved.</span></span>|  
|`pmMaxValue`|<span data-ttu-id="0f48f-139">Зарезервировано.</span><span class="sxs-lookup"><span data-stu-id="0f48f-139">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0f48f-140">Требования</span><span class="sxs-lookup"><span data-stu-id="0f48f-140">Requirements</span></span>  
 <span data-ttu-id="0f48f-141">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f48f-141">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f48f-142">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="0f48f-142">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0f48f-143">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f48f-143">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f48f-144">См. также статью</span><span class="sxs-lookup"><span data-stu-id="0f48f-144">See also</span></span>

- [<span data-ttu-id="0f48f-145">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0f48f-145">Metadata Enumerations</span></span>](metadata-enumerations.md)
