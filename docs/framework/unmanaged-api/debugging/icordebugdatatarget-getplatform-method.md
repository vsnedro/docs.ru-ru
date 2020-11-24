---
title: Метод ICorDebugDataTarget::GetPlatform
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetPlatform Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetPlatform
helpviewer_keywords:
- GetPlatform method [.NET Framework debugging]
- ICorDebugDataTarget::GetPlatform method [.NET Framework debugging]
ms.assetid: 9ee96c9d-7a3d-4129-a6cc-7675c7f2dda4
topic_type:
- apiref
ms.openlocfilehash: e8612b23cbfa506fddb2fad712848b285b9ac28e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679797"
---
# <a name="icordebugdatatargetgetplatform-method"></a><span data-ttu-id="93e9e-102">Метод ICorDebugDataTarget::GetPlatform</span><span class="sxs-lookup"><span data-stu-id="93e9e-102">ICorDebugDataTarget::GetPlatform Method</span></span>

<span data-ttu-id="93e9e-103">Предоставляет сведения о платформе, включая архитектуру процессора и операционную систему, на которых выполняется целевой процесс.</span><span class="sxs-lookup"><span data-stu-id="93e9e-103">Provides information about the platform, including processor architecture and operating system, on which the target process is running.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93e9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="93e9e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPlatform([out] CorDebugPlatform * pTargetPlatform);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93e9e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="93e9e-105">Parameters</span></span>  

 `pTargetPlatform`  
 <span data-ttu-id="93e9e-106">заполняет Указатель на перечисление [кордебугплатформенум](cordebugplatform-enumeration.md) , описывающее целевую платформу.</span><span class="sxs-lookup"><span data-stu-id="93e9e-106">[out] A pointer to a [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration that describes the target platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93e9e-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="93e9e-107">Remarks</span></span>  

 <span data-ttu-id="93e9e-108">`CorDebugPlatformEnum`Возвращаемое значение перечисления используется интерфейсом [ICorDebug](icordebug-interface.md) для определения сведений о целевом процессе, таких как размер указателя, макет адресного пространства, набор регистров, формат инструкций, контекстный макет и соглашения о вызовах.</span><span class="sxs-lookup"><span data-stu-id="93e9e-108">The `CorDebugPlatformEnum` enumeration return value is used by the [ICorDebug](icordebug-interface.md) interface to determine details of the target process such as its pointer size, address space layout, register set, instruction format, context layout, and calling conventions.</span></span>  
  
 <span data-ttu-id="93e9e-109">`pTargetPlatform`Значение может ссылаться на платформу, которая эмулируется для целевого объекта, вместо того, чтобы указывать фактическое используемое оборудование.</span><span class="sxs-lookup"><span data-stu-id="93e9e-109">The `pTargetPlatform` value may refer to a platform that is being emulated for the target instead of specifying the actual hardware in use.</span></span> <span data-ttu-id="93e9e-110">Например, процесс, выполняемый в среде Windows on Windows (WOW) в 64-разрядном выпуске операционной системы Windows, должен использовать `CORDB_PLATFORM_WINDOWS_X86` значение перечисления [кордебугплатформенум](cordebugplatform-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="93e9e-110">For example, a process that is running in the Windows on Windows (WOW) environment on a 64-bit edition of the Windows operating system should use the `CORDB_PLATFORM_WINDOWS_X86` value of the [CorDebugPlatformEnum](cordebugplatform-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="93e9e-111">Этот метод должен быть выполнен.</span><span class="sxs-lookup"><span data-stu-id="93e9e-111">This method must succeed.</span></span> <span data-ttu-id="93e9e-112">В случае сбоя Целевая платформа будет непригодна для использования.</span><span class="sxs-lookup"><span data-stu-id="93e9e-112">If it fails, the target platform is unusable.</span></span> <span data-ttu-id="93e9e-113">Метод может завершиться ошибкой по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="93e9e-113">The method may fail for the following reasons:</span></span>  
  
- <span data-ttu-id="93e9e-114">Платформа, которая эмулируется для целевого объекта, непригодна для использования.</span><span class="sxs-lookup"><span data-stu-id="93e9e-114">The platform that is being emulated for the target is unusable.</span></span>  
  
- <span data-ttu-id="93e9e-115">Фактическое оборудование на целевой платформе непригодно для использования.</span><span class="sxs-lookup"><span data-stu-id="93e9e-115">The actual hardware on the target platform is unusable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93e9e-116">Требования</span><span class="sxs-lookup"><span data-stu-id="93e9e-116">Requirements</span></span>  

 <span data-ttu-id="93e9e-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93e9e-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93e9e-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="93e9e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="93e9e-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="93e9e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="93e9e-120">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93e9e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e9e-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="93e9e-121">See also</span></span>

- [<span data-ttu-id="93e9e-122">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="93e9e-122">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="93e9e-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="93e9e-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="93e9e-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="93e9e-124">Debugging</span></span>](index.md)
