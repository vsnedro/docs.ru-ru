---
title: Метод ICorDebugILFrame::EnumerateLocalVariables
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 968ceec53aade3d04c500c8247d397ffb71382c1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703204"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="951e8-102">Метод ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="951e8-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>

<span data-ttu-id="951e8-103">Возвращает перечислитель для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="951e8-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="951e8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="951e8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="951e8-105">Parameters</span></span>  

 `ppValueEnum`  
 <span data-ttu-id="951e8-106">[из] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в этом кадре.</span><span class="sxs-lookup"><span data-stu-id="951e8-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="951e8-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="951e8-107">Remarks</span></span>  

 <span data-ttu-id="951e8-108">`EnumerateLocalVariables` Возвращает перечислитель, который может перечислить локальные переменные, доступные в кадре вызова, представленном этим объектом ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="951e8-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="951e8-109">Список не может включать все локальные переменные в выполняемой функции, так как некоторые из них могут быть неактивными.</span><span class="sxs-lookup"><span data-stu-id="951e8-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="951e8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="951e8-110">Requirements</span></span>  

 <span data-ttu-id="951e8-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="951e8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="951e8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="951e8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="951e8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="951e8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="951e8-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="951e8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
