---
title: Метод ICorDebugRegisterSet::SetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
ms.openlocfilehash: 4be5d2d9d891010e68cd6eb96cd4456e04d8c8b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712291"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="ca7b5-102">Метод ICorDebugRegisterSet::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="ca7b5-102">ICorDebugRegisterSet::SetRegisters Method</span></span>

<span data-ttu-id="ca7b5-103">`SetRegisters` не реализован в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="ca7b5-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ca7b5-104">Этот метод не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="ca7b5-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca7b5-105">Используйте операции более высокого уровня, такие как [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) или [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="ca7b5-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca7b5-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca7b5-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ca7b5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ca7b5-107">Requirements</span></span>  

 <span data-ttu-id="ca7b5-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca7b5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca7b5-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca7b5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca7b5-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca7b5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca7b5-111">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="ca7b5-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7b5-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ca7b5-112">See also</span></span>

- [<span data-ttu-id="ca7b5-113">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="ca7b5-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="ca7b5-114">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="ca7b5-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
