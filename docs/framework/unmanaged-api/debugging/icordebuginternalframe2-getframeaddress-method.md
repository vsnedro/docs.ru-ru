---
title: Метод ICorDebugInternalFrame2::GetFrameAddress
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.GetFrameAddress Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::GetFrameAddress
helpviewer_keywords:
- GetFrameAddress method [.NET Framework debugging]
- ICorDebugInternalFrame2::GetFrameAddress method [.NET Framework debugging]
ms.assetid: 4ee8d058-ffc8-4967-9133-a5adfef4e518
topic_type:
- apiref
ms.openlocfilehash: 05a9ab58acb3bf5829fd231ae6d8bcc96ae06da6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724875"
---
# <a name="icordebuginternalframe2getframeaddress-method"></a><span data-ttu-id="2b8ef-102">Метод ICorDebugInternalFrame2::GetFrameAddress</span><span class="sxs-lookup"><span data-stu-id="2b8ef-102">ICorDebugInternalFrame2::GetFrameAddress Method</span></span>

<span data-ttu-id="2b8ef-103">Возвращает адрес стека внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-103">Returns the stack address of the internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b8ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b8ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameAddress([out] CORDB_ADDRESS *pAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b8ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b8ef-105">Parameters</span></span>  

 `pAddress`  
 <span data-ttu-id="2b8ef-106">заполняет Указатель на объект `CORDB_ADDRESS` для внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-106">[out] Pointer to the `CORDB_ADDRESS` for the internal frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b8ef-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2b8ef-107">Return Value</span></span>  

 <span data-ttu-id="2b8ef-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2b8ef-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b8ef-109">HRESULT</span></span>|<span data-ttu-id="2b8ef-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="2b8ef-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b8ef-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b8ef-111">S_OK</span></span>|<span data-ttu-id="2b8ef-112">Адрес внутреннего кадра успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-112">The address of the internal frame was successfully returned.</span></span>|  
|<span data-ttu-id="2b8ef-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b8ef-113">E_FAIL</span></span>|<span data-ttu-id="2b8ef-114">Не удалось вернуть адрес внутреннего кадра.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-114">The address of the internal frame could not be returned.</span></span>|  
|<span data-ttu-id="2b8ef-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2b8ef-115">E_INVALIDARG</span></span>|<span data-ttu-id="2b8ef-116">`pAddress` имеет значение `null`.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-116">`pAddress` is `null`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b8ef-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2b8ef-117">Remarks</span></span>  

 <span data-ttu-id="2b8ef-118">Значение, возвращаемое в, `pAddress` можно использовать для определения расположения внутреннего кадра относительно других кадров в стеке.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-118">The value returned in `pAddress` can be used to determine the location of the internal frame relative to other frames on the stack.</span></span> <span data-ttu-id="2b8ef-119">Даже на компьютерах на базе IA-64 внутренний кадр находится только в стеке и не имеет соответствующего указателя на резервное хранилище.</span><span class="sxs-lookup"><span data-stu-id="2b8ef-119">Even on IA-64-based computers, the internal frame lives on the stack only, and there is no corresponding pointer to a backing store.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b8ef-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2b8ef-120">Requirements</span></span>  

 <span data-ttu-id="2b8ef-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b8ef-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b8ef-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b8ef-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b8ef-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b8ef-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b8ef-124">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b8ef-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b8ef-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2b8ef-125">See also</span></span>

- [<span data-ttu-id="2b8ef-126">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="2b8ef-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="2b8ef-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2b8ef-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2b8ef-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="2b8ef-128">Debugging</span></span>](index.md)
