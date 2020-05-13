---
title: Метод ICorDebugRegisterSet::SetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
ms.openlocfilehash: 63ddce2f299133fcfe0da17897eaf0c6a9509a55
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378245"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="f608d-102">Метод ICorDebugRegisterSet::SetThreadContext</span><span class="sxs-lookup"><span data-stu-id="f608d-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="f608d-103">`SetThreadContext`не реализован в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="f608d-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f608d-104">Этот метод не следует вызывать.</span><span class="sxs-lookup"><span data-stu-id="f608d-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f608d-105">Используйте операцию более высокого уровня [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md) , чтобы задать контекст потока.</span><span class="sxs-lookup"><span data-stu-id="f608d-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f608d-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f608d-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f608d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="f608d-107">Requirements</span></span>  
 <span data-ttu-id="f608d-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f608d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f608d-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f608d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f608d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f608d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f608d-111">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="f608d-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f608d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="f608d-112">See also</span></span>

- [<span data-ttu-id="f608d-113">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="f608d-113">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="f608d-114">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="f608d-114">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
