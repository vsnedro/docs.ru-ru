---
title: Метод ICorDebugRegisterSet2::SetRegisters
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
ms.openlocfilehash: ebbd8dc2b715541850ed3b3bc530c0dd28993e1d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378129"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="ca0b1-102">Метод ICorDebugRegisterSet2::SetRegisters</span><span class="sxs-lookup"><span data-stu-id="ca0b1-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="ca0b1-103">`SetRegisters`не реализован в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="ca0b1-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ca0b1-104">Этот метод не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="ca0b1-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca0b1-105">Используйте операции более высокого уровня, такие как [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) или [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="ca0b1-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca0b1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca0b1-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ca0b1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ca0b1-107">Requirements</span></span>  
 <span data-ttu-id="ca0b1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca0b1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca0b1-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca0b1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca0b1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca0b1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca0b1-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca0b1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca0b1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ca0b1-112">See also</span></span>

- [<span data-ttu-id="ca0b1-113">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="ca0b1-113">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="ca0b1-114">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="ca0b1-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
