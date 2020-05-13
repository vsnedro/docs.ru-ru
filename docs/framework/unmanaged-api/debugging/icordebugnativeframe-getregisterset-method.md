---
title: Метод ICorDebugNativeFrame::GetRegisterSet
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
ms.openlocfilehash: e2055098c85c5a2e4619b9b0ddc8d602256bd16b
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209725"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="c9da1-102">Метод ICorDebugNativeFrame::GetRegisterSet</span><span class="sxs-lookup"><span data-stu-id="c9da1-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="c9da1-103">Возвращает набор регистров для этого кадра стека.</span><span class="sxs-lookup"><span data-stu-id="c9da1-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9da1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c9da1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9da1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c9da1-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="c9da1-106">заполняет Указатель на адрес объекта [ICorDebugRegisterSet](icordebugregisterset-interface.md) , который представляет набор регистров для данного кадра стека.</span><span class="sxs-lookup"><span data-stu-id="c9da1-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9da1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c9da1-107">Requirements</span></span>  
 <span data-ttu-id="c9da1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9da1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9da1-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c9da1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9da1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9da1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9da1-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9da1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9da1-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c9da1-112">See also</span></span>
