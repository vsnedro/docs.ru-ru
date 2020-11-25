---
title: Метод ICorDebugInternalFrame2::IsCloserToLeaf
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame2.IsCloserToLeaf Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf
helpviewer_keywords:
- ICorDebugInternalFrame2::IsCloserToLeaf method [.NET Framework debugging]
- IsCloserToLeaf method [.NET Framework debugging]
ms.assetid: c1d3d1eb-8370-4f25-8297-3bd262b4740a
topic_type:
- apiref
ms.openlocfilehash: 83d3eda0f3c4619ec7a5df91d13ab9f3a58e5f01
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721352"
---
# <a name="icordebuginternalframe2isclosertoleaf-method"></a><span data-ttu-id="94448-102">Метод ICorDebugInternalFrame2::IsCloserToLeaf</span><span class="sxs-lookup"><span data-stu-id="94448-102">ICorDebugInternalFrame2::IsCloserToLeaf Method</span></span>

<span data-ttu-id="94448-103">Проверяет, `this` находится ли внутренний кадр ближе к конечному объекту, чем указанный объект ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="94448-103">Checks whether the `this` internal frame is closer to the leaf than the specified ICorDebugFrame object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94448-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="94448-104">Syntax</span></span>  
  
```cpp  
HRESULT IsCloserToLeaf([in] ICorDebugFrame * pFrameToCompare,  
                       [out] BOOL * pIsCloser);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94448-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="94448-105">Parameters</span></span>  

 `pFrameToCompare`  
 <span data-ttu-id="94448-106">окне Указатель на `ICorDebugFrame` объект сравнения.</span><span class="sxs-lookup"><span data-stu-id="94448-106">[in] A pointer to the comparison `ICorDebugFrame` object.</span></span>  
  
 `pIsCloser`  
 <span data-ttu-id="94448-107">[out] `true` `this` значение, если внутренний кадр находится ближе к конечному объекту, чем кадр, заданный параметром `pFrameToCompare` ; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="94448-107">[out] `true` if the `this` internal frame is closer to the leaf than the frame specified by `pFrameToCompare`; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="94448-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="94448-108">Return Value</span></span>  

 <span data-ttu-id="94448-109">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="94448-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="94448-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="94448-110">HRESULT</span></span>|<span data-ttu-id="94448-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="94448-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="94448-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="94448-112">S_OK</span></span>|<span data-ttu-id="94448-113">Сравнение успешно выполнено.</span><span class="sxs-lookup"><span data-stu-id="94448-113">The comparison was successfully performed.</span></span>|  
|<span data-ttu-id="94448-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="94448-114">E_FAIL</span></span>|<span data-ttu-id="94448-115">Не удалось выполнить сравнение.</span><span class="sxs-lookup"><span data-stu-id="94448-115">The comparison could not be performed.</span></span>|  
|<span data-ttu-id="94448-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="94448-116">E_INVALIDARG</span></span>|<span data-ttu-id="94448-117">`pFrameToCompare` или `pIsCloser` равно null.</span><span class="sxs-lookup"><span data-stu-id="94448-117">`pFrameToCompare` or `pIsCloser` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="94448-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="94448-118">Remarks</span></span>  

 <span data-ttu-id="94448-119">`IsCloserToLeaf` может использоваться для реализации политики для поверх внутренних кадров с другими кадрами в стеке.</span><span class="sxs-lookup"><span data-stu-id="94448-119">`IsCloserToLeaf` can be used to implement a policy for interleaving internal frames with other frames on the stack.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94448-120">Требования</span><span class="sxs-lookup"><span data-stu-id="94448-120">Requirements</span></span>  

 <span data-ttu-id="94448-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94448-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94448-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94448-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94448-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94448-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94448-124">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94448-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94448-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="94448-125">See also</span></span>

- [<span data-ttu-id="94448-126">Интерфейс ICorDebugInternalFrame2</span><span class="sxs-lookup"><span data-stu-id="94448-126">ICorDebugInternalFrame2 Interface</span></span>](icordebuginternalframe2-interface.md)
- [<span data-ttu-id="94448-127">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="94448-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="94448-128">Отладка</span><span class="sxs-lookup"><span data-stu-id="94448-128">Debugging</span></span>](index.md)
