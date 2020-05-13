---
title: Метод ICorDebugManagedCallback::ControlCTrap
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.ControlCTrap
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::ControlCTrap
helpviewer_keywords:
- ICorDebugManagedCallback::ControlCTrap method [.NET Framework debugging]
- ControlCTrap method [.NET Framework debugging]
ms.assetid: 0500854e-2121-43d9-a028-64312da35258
topic_type:
- apiref
ms.openlocfilehash: 33a68d11a8d17e46533b4f83bbf87aafe171e612
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212403"
---
# <a name="icordebugmanagedcallbackcontrolctrap-method"></a><span data-ttu-id="56b21-102">Метод ICorDebugManagedCallback::ControlCTrap</span><span class="sxs-lookup"><span data-stu-id="56b21-102">ICorDebugManagedCallback::ControlCTrap Method</span></span>
<span data-ttu-id="56b21-103">Уведомляет отладчик о том, что в отлаживаемом процессе выполняется перехват CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="56b21-103">Notifies the debugger that a CTRL+C is trapped in the process that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56b21-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56b21-104">Syntax</span></span>  
  
```cpp  
HRESULT ControlCTrap (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="56b21-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="56b21-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="56b21-106">окне Указатель на объект ICorDebugProcess, представляющий процесс, в котором выполняется перехват CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="56b21-106">[in] A pointer to an ICorDebugProcess object that represents the process in which the CTRL+C is trapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="56b21-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="56b21-107">Return Value</span></span>  
  
|<span data-ttu-id="56b21-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="56b21-108">HRESULT</span></span>|<span data-ttu-id="56b21-109">Описание</span><span class="sxs-lookup"><span data-stu-id="56b21-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="56b21-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="56b21-110">S_OK</span></span>|<span data-ttu-id="56b21-111">Отладчик будет выполнять обработку ловушек CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="56b21-111">The debugger will handle the CTRL+C trap.</span></span>|  
|<span data-ttu-id="56b21-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="56b21-112">S_FALSE</span></span>|<span data-ttu-id="56b21-113">Отладчик не будет выполнять обработку ловушек CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="56b21-113">The debugger will not handle the CTRL+C trap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="56b21-114">Remarks</span><span class="sxs-lookup"><span data-stu-id="56b21-114">Remarks</span></span>  
 <span data-ttu-id="56b21-115">Все домены приложений в рамках процесса останавливаются для этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="56b21-115">All application domains within the process are stopped for this callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="56b21-116">Требования</span><span class="sxs-lookup"><span data-stu-id="56b21-116">Requirements</span></span>  
 <span data-ttu-id="56b21-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="56b21-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56b21-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="56b21-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="56b21-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="56b21-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="56b21-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56b21-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56b21-121">См. также</span><span class="sxs-lookup"><span data-stu-id="56b21-121">See also</span></span>

- [<span data-ttu-id="56b21-122">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="56b21-122">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
