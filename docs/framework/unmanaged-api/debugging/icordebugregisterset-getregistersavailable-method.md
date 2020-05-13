---
title: Метод ICorDebugRegisterSet::GetRegistersAvailable
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetRegistersAvailable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable
helpviewer_keywords:
- ICorDebugRegisterSet::GetRegistersAvailable method [.NET Framework debugging]
- GetRegistersAvailable method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 4ba08ffa-55a2-4662-9d6d-4738f1db60c9
topic_type:
- apiref
ms.openlocfilehash: 74eef0c1ec456d647e5a58e5009d2c77e5002289
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378295"
---
# <a name="icordebugregistersetgetregistersavailable-method"></a><span data-ttu-id="b8d05-102">Метод ICorDebugRegisterSet::GetRegistersAvailable</span><span class="sxs-lookup"><span data-stu-id="b8d05-102">ICorDebugRegisterSet::GetRegistersAvailable Method</span></span>
<span data-ttu-id="b8d05-103">Возвращает битовую маску, указывающую, какие регистры в этом [ICorDebugRegisterSet](icordebugregisterset-interface.md) в настоящее время доступны.</span><span class="sxs-lookup"><span data-stu-id="b8d05-103">Gets a bit mask indicating which registers in this [ICorDebugRegisterSet](icordebugregisterset-interface.md) are currently available.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8d05-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b8d05-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegistersAvailable (  
    [out] ULONG64   *pAvailable  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8d05-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b8d05-105">Parameters</span></span>  
 `pAvailable`  
 <span data-ttu-id="b8d05-106">заполняет Битовая маска, указывающая, какие регистры доступны в настоящее время.</span><span class="sxs-lookup"><span data-stu-id="b8d05-106">[out] A bit mask that indicates which registers are currently available.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8d05-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8d05-107">Remarks</span></span>  
 <span data-ttu-id="b8d05-108">Регистр может быть недоступен, если его значение не может быть определено для данной ситуации.</span><span class="sxs-lookup"><span data-stu-id="b8d05-108">A register may be unavailable if its value cannot be determined for the given situation.</span></span>  
  
 <span data-ttu-id="b8d05-109">Возвращаемая маска содержит бит для каждого регистра (1 << индекс регистра).</span><span class="sxs-lookup"><span data-stu-id="b8d05-109">The returned mask contains a bit for each register (1 << the register index).</span></span> <span data-ttu-id="b8d05-110">Значение бита равно 1, если регистр доступен, или 0, если он недоступен.</span><span class="sxs-lookup"><span data-stu-id="b8d05-110">The bit value is 1 if the register is available, or 0 if it is not available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8d05-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b8d05-111">Requirements</span></span>  
 <span data-ttu-id="b8d05-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8d05-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8d05-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8d05-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8d05-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8d05-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8d05-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8d05-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d05-116">См. также</span><span class="sxs-lookup"><span data-stu-id="b8d05-116">See also</span></span>

- [<span data-ttu-id="b8d05-117">Интерфейс ICorDebugRegisterSet</span><span class="sxs-lookup"><span data-stu-id="b8d05-117">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="b8d05-118">Интерфейс ICorDebugRegisterSet2</span><span class="sxs-lookup"><span data-stu-id="b8d05-118">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
