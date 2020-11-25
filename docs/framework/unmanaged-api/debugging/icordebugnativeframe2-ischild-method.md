---
title: Метод ICorDebugNativeFrame2::IsChild
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsChild Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsChild
helpviewer_keywords:
- IsChild method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsChild method [.NET Framework debugging]
ms.assetid: 9e2aae09-49cb-4fbd-81e5-e29cd864a88b
topic_type:
- apiref
ms.openlocfilehash: 0d65849aba08c7d143a6977e7dfb8cff85274a64
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695573"
---
# <a name="icordebugnativeframe2ischild-method"></a><span data-ttu-id="15f1b-102">Метод ICorDebugNativeFrame2::IsChild</span><span class="sxs-lookup"><span data-stu-id="15f1b-102">ICorDebugNativeFrame2::IsChild Method</span></span>

<span data-ttu-id="15f1b-103">Определяет, является ли текущий кадр дочерним кадром.</span><span class="sxs-lookup"><span data-stu-id="15f1b-103">Determines whether the current frame is a child frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15f1b-104">Syntax</span></span>  
  
```cpp  
HRESULT IsChild([out] BOOL * pIsChild);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15f1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15f1b-105">Parameters</span></span>  

 `pIsChild`  
 <span data-ttu-id="15f1b-106">заполняет Логическое значение, указывающее, является ли текущий кадр дочерним кадром.</span><span class="sxs-lookup"><span data-stu-id="15f1b-106">[out] A Boolean value that specifies whether the current frame is a child frame.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="15f1b-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="15f1b-107">Return Value</span></span>  

 <span data-ttu-id="15f1b-108">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="15f1b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="15f1b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="15f1b-109">HRESULT</span></span>|<span data-ttu-id="15f1b-110">Описание:</span><span class="sxs-lookup"><span data-stu-id="15f1b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="15f1b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="15f1b-111">S_OK</span></span>|<span data-ttu-id="15f1b-112">Состояние дочернего элемента успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="15f1b-112">The child status was successfully returned.</span></span>|  
|<span data-ttu-id="15f1b-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="15f1b-113">E_FAIL</span></span>|<span data-ttu-id="15f1b-114">Не удалось вернуть состояние дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="15f1b-114">The child status could not be returned.</span></span>|  
|<span data-ttu-id="15f1b-115">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="15f1b-115">E_INVALIDARG</span></span>|<span data-ttu-id="15f1b-116">Параметр `pIsChild` имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="15f1b-116">`pIsChild` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="15f1b-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="15f1b-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15f1b-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="15f1b-118">Remarks</span></span>  

 <span data-ttu-id="15f1b-119">`IsChild`Метод возвращает значение, `true` Если объект Frame, для которого вызывается метод, является дочерним по отношению к другому кадру.</span><span class="sxs-lookup"><span data-stu-id="15f1b-119">The `IsChild` method returns `true` if the frame object on which you call the method is a child of another frame.</span></span> <span data-ttu-id="15f1b-120">В этом случае используйте метод [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) , чтобы проверить, является ли кадр родительским.</span><span class="sxs-lookup"><span data-stu-id="15f1b-120">If this is the case, use the [IsMatchingParentFrame](icordebugnativeframe2-ismatchingparentframe-method.md) method to check whether a frame is its parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f1b-121">Требования</span><span class="sxs-lookup"><span data-stu-id="15f1b-121">Requirements</span></span>  

 <span data-ttu-id="15f1b-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f1b-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f1b-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15f1b-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15f1b-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15f1b-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15f1b-125">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f1b-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f1b-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15f1b-126">See also</span></span>

- [<span data-ttu-id="15f1b-127">Интерфейс ICorDebugNativeFrame2</span><span class="sxs-lookup"><span data-stu-id="15f1b-127">ICorDebugNativeFrame2 Interface</span></span>](icordebugnativeframe2-interface.md)
- [<span data-ttu-id="15f1b-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="15f1b-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="15f1b-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="15f1b-129">Debugging</span></span>](index.md)
