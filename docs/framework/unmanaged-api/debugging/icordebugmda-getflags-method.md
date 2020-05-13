---
title: Метод ICorDebugMDA::GetFlags
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetFlags
helpviewer_keywords:
- ICorDebugMDA::GetFlags method [.NET Framework debugging]
- GetFlags method [.NET Framework debugging]
ms.assetid: 87ce7c5b-fd82-453e-bf55-c8a32150b183
topic_type:
- apiref
ms.openlocfilehash: 4e5939e9e74899a33f28927c4fda09d0a8fb30a0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209738"
---
# <a name="icordebugmdagetflags-method"></a><span data-ttu-id="e33cb-102">Метод ICorDebugMDA::GetFlags</span><span class="sxs-lookup"><span data-stu-id="e33cb-102">ICorDebugMDA::GetFlags Method</span></span>
<span data-ttu-id="e33cb-103">Возвращает флаги, связанные с помощником по отладке управляемого кода (MDA), представленным [ICorDebugMDA](icordebugmda-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e33cb-103">Gets the flags associated with the managed debugging assistant (MDA) represented by [ICorDebugMDA](icordebugmda-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e33cb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e33cb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags (  
    [in] CorDebugMDAFlags *pFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e33cb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e33cb-105">Parameters</span></span>  
 `pFlags`  
 <span data-ttu-id="e33cb-106">окне Побитовое сочетание значений перечисления [кордебугмдафлагс](cordebugmdaflags-enumeration.md) , определяющих параметры флагов для этого MDA.</span><span class="sxs-lookup"><span data-stu-id="e33cb-106">[in] A bitwise combination of the [CorDebugMDAFlags](cordebugmdaflags-enumeration.md) enumeration values that specify the settings of the flags for this MDA.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e33cb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e33cb-107">Requirements</span></span>  
 <span data-ttu-id="e33cb-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e33cb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e33cb-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e33cb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e33cb-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e33cb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e33cb-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e33cb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33cb-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e33cb-112">See also</span></span>

- [<span data-ttu-id="e33cb-113">Интерфейс ICorDebugMDA</span><span class="sxs-lookup"><span data-stu-id="e33cb-113">ICorDebugMDA Interface</span></span>](icordebugmda-interface.md)
- [<span data-ttu-id="e33cb-114">Диагностика ошибок посредством управляемых помощников по отладке</span><span class="sxs-lookup"><span data-stu-id="e33cb-114">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
