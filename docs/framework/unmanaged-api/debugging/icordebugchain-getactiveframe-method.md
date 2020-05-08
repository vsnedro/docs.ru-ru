---
title: Метод ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
ms.openlocfilehash: 2f67188539d5ad5523c255fbc663e990e1b8245f
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894681"
---
# <a name="icordebugchaingetactiveframe-method"></a><span data-ttu-id="09d06-102">Метод ICorDebugChain::GetActiveFrame</span><span class="sxs-lookup"><span data-stu-id="09d06-102">ICorDebugChain::GetActiveFrame Method</span></span>
<span data-ttu-id="09d06-103">Возвращает активный (то есть самый последний) кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="09d06-103">Gets the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d06-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09d06-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09d06-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09d06-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="09d06-106">заполняет Указатель на адрес объекта ICorDebugFrame, который представляет активный (то есть самый последний) кадр в цепочке.</span><span class="sxs-lookup"><span data-stu-id="09d06-106">[out] A pointer to the address of an ICorDebugFrame object that represents the active (that is, most recent) frame on the chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09d06-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="09d06-107">Remarks</span></span>  
 <span data-ttu-id="09d06-108">Если управляемый фрейм стека недоступен, `ppFrame` устанавливается в значение null.</span><span class="sxs-lookup"><span data-stu-id="09d06-108">If no managed stack frame is available, `ppFrame` is set to null.</span></span>  
  
 <span data-ttu-id="09d06-109">Если активный кадр недоступен, вызов будет выполнен и `ppFrame` будет иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="09d06-109">If the active frame is not available, the call will succeed and `ppFrame` will be null.</span></span> <span data-ttu-id="09d06-110">Активные фреймы не будут доступны для цепочек, инициированных из-за CHAIN_ENTER_UNMANAGED, и для некоторых цепочек, инициированных из-за CHAIN_CLASS_INIT.</span><span class="sxs-lookup"><span data-stu-id="09d06-110">Active frames will not be available for chains initiated due to CHAIN_ENTER_UNMANAGED, and for some chains initiated due to CHAIN_CLASS_INIT.</span></span> <span data-ttu-id="09d06-111">См. раздел перечисление Кордебугчаинреасон.</span><span class="sxs-lookup"><span data-stu-id="09d06-111">See the CorDebugChainReason enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09d06-112">Требования</span><span class="sxs-lookup"><span data-stu-id="09d06-112">Requirements</span></span>  
 <span data-ttu-id="09d06-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09d06-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d06-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09d06-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09d06-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09d06-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09d06-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d06-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
