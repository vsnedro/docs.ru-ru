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
ms.openlocfilehash: f2850e6c9cbb2250a08ab4a0e34c69e377d3a23d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83375851"
---
# <a name="icordebugthread3createstackwalk-method"></a><span data-ttu-id="66c3e-102">Метод ICorDebugThread3::CreateStackWalk</span><span class="sxs-lookup"><span data-stu-id="66c3e-102">ICorDebugThread3::CreateStackWalk Method</span></span>
<span data-ttu-id="66c3e-103">Создает объект [икордебугстакквалк](icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="66c3e-103">Creates an [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66c3e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66c3e-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStackWalk([out] ICorDebugStackWalk **ppStackWalk);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66c3e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66c3e-105">Parameters</span></span>  
 `ppStackWalk`  
 <span data-ttu-id="66c3e-106">заполняет Указатель на адрес объекта [икордебугстакквалк](icordebugstackwalk-interface.md) для потока, стек которого нужно очистить.</span><span class="sxs-lookup"><span data-stu-id="66c3e-106">[out] A pointer to address of the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object for the thread whose stack you want to unwind.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="66c3e-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="66c3e-107">Return Value</span></span>  
 <span data-ttu-id="66c3e-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="66c3e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="66c3e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="66c3e-109">HRESULT</span></span>|<span data-ttu-id="66c3e-110">Описание</span><span class="sxs-lookup"><span data-stu-id="66c3e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="66c3e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="66c3e-111">S_OK</span></span>|<span data-ttu-id="66c3e-112">`ICorDebugStackWalk`Объект успешно создан.</span><span class="sxs-lookup"><span data-stu-id="66c3e-112">The `ICorDebugStackWalk` object was successfully created.</span></span>|  
|<span data-ttu-id="66c3e-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="66c3e-113">E_FAIL</span></span>|<span data-ttu-id="66c3e-114">`ICorDebugStackWalk`Объект не был создан.</span><span class="sxs-lookup"><span data-stu-id="66c3e-114">The `ICorDebugStackWalk` object was not created.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="66c3e-115">Исключения</span><span class="sxs-lookup"><span data-stu-id="66c3e-115">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66c3e-116">Remarks</span><span class="sxs-lookup"><span data-stu-id="66c3e-116">Remarks</span></span>  
 <span data-ttu-id="66c3e-117">Если `CreateStackWalk` метод выполнен, контекст возвращаемого `ICorDebugStackWalk` объекта устанавливается в текущий контекст потока.</span><span class="sxs-lookup"><span data-stu-id="66c3e-117">If the `CreateStackWalk` method succeeds, the returned `ICorDebugStackWalk` object's context is set to the thread's current context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66c3e-118">Требования</span><span class="sxs-lookup"><span data-stu-id="66c3e-118">Requirements</span></span>  
 <span data-ttu-id="66c3e-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66c3e-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66c3e-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66c3e-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66c3e-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66c3e-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66c3e-122">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66c3e-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66c3e-123">См. также</span><span class="sxs-lookup"><span data-stu-id="66c3e-123">See also</span></span>

- [<span data-ttu-id="66c3e-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="66c3e-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="66c3e-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="66c3e-125">Debugging</span></span>](index.md)
