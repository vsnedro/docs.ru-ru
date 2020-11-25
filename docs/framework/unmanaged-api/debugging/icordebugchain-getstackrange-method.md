---
title: Метод ICorDebugChain::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetStackRange
helpviewer_keywords:
- ICorDebugChain::GetStackRange method [.NET Framework debugging]
- GetStackRange method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 554284e7-3f6c-4d40-8da5-1c9317fbd484
topic_type:
- apiref
ms.openlocfilehash: 841e3ca608d20a4b8618508e69195de0b1da1341
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724407"
---
# <a name="icordebugchaingetstackrange-method"></a><span data-ttu-id="181bb-102">Метод ICorDebugChain::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="181bb-102">ICorDebugChain::GetStackRange Method</span></span>

<span data-ttu-id="181bb-103">Возвращает диапазон адресов сегмента стека для этой цепочки.</span><span class="sxs-lookup"><span data-stu-id="181bb-103">Gets the address range of the stack segment for this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="181bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="181bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="181bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="181bb-105">Parameters</span></span>  

 `pStart`  
 <span data-ttu-id="181bb-106">заполняет Указатель на `CORDB_ADDRESS` значение, которое является начальным адресом сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="181bb-106">[out] A pointer to a `CORDB_ADDRESS` value that is the starting address of the stack segment.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="181bb-107">заполняет Указатель на `CORDB_ADDRESS` значение, которое является конечным адресом сегмента стека.</span><span class="sxs-lookup"><span data-stu-id="181bb-107">[out] A pointer to a `CORDB_ADDRESS` value that is the ending address of the stack segment.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="181bb-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="181bb-108">Remarks</span></span>  

 <span data-ttu-id="181bb-109">Числовой диапазон имеет смысл только для сравнения расположений в кадрах стека.</span><span class="sxs-lookup"><span data-stu-id="181bb-109">The numeric range is meaningful only for comparison of stack frame locations.</span></span> <span data-ttu-id="181bb-110">Вы не можете делать предположения о том, что фактически хранится в стеке.</span><span class="sxs-lookup"><span data-stu-id="181bb-110">You cannot make any assumptions about what is actually stored on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="181bb-111">Требования</span><span class="sxs-lookup"><span data-stu-id="181bb-111">Requirements</span></span>  

 <span data-ttu-id="181bb-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="181bb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="181bb-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="181bb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="181bb-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="181bb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="181bb-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="181bb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
