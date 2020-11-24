---
title: Метод ICorDebugThread3::CreateStackWalk
ms.date: 03/30/2017
api_name:
- ICorDebugThread3.CreateStackWalk Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread3::CreateStackWalk
helpviewer_keywords:
- CreateStackWalk method [.NET Framework debugging]
- ICorDebugThread3::CreateStackWalk method [.NET Framework debugging]
ms.assetid: c55e35d9-f9aa-4268-94b5-dce44c61acf2
topic_type:
- apiref
ms.openlocfilehash: fb9d07fffd2ec98225ce60b211f525f8dafd9725
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95691073"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="39193-102">Метод ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="39193-102">ICorDebugThread3::CreateStackWalk Method</span></span>

<span data-ttu-id="39193-103">Создает объект [икордебугстакквалк](icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="39193-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39193-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39193-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39193-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="39193-105">Parameters</span></span>  

 `ppStackWalk`  
 <span data-ttu-id="39193-106">заполняет Указатель на адрес объекта [икордебугстакквалк](icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="39193-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="39193-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="39193-107">Return Value</span></span>  

 <span data-ttu-id="39193-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="39193-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="39193-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="39193-109">HRESULT</span></span>|<span data-ttu-id="39193-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="39193-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="39193-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="39193-111">S_OK</span></span>|<span data-ttu-id="39193-112">`ICorDebugStackWalk`Объект успешно создан.</span><span class="sxs-lookup"><span data-stu-id="39193-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="39193-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="39193-113">E_FAIL</span></span>|<span data-ttu-id="39193-114">`ICorDebugStackWalk`Объект не был создан.</span><span class="sxs-lookup"><span data-stu-id="39193-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="39193-115">Исключения</span><span class="sxs-lookup"><span data-stu-id="39193-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39193-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="39193-116">Remarks</span></span>  

 <span data-ttu-id="39193-117">Если `CreateStackWalk` метод выполнен, контекст возвращаемого `ICorDebugStackWalk` объекта устанавливается в текущий контекст потока.</span><span class="sxs-lookup"><span data-stu-id="39193-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39193-118">Требования</span><span class="sxs-lookup"><span data-stu-id="39193-118">Requirements</span></span>  

 <span data-ttu-id="39193-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39193-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39193-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39193-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39193-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39193-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39193-122">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39193-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39193-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="39193-123">See also</span></span>

- [<span data-ttu-id="39193-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="39193-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="39193-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="39193-125">Debugging</span></span>](index.md)
