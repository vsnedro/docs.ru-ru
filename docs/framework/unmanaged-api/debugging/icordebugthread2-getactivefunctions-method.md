---
title: Метод ICorDebugThread2::GetActiveFunctions
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
ms.openlocfilehash: 2d5674d6b5962ca539de02cda1e5658daed83622
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678757"
---
# <a name="icordebugthread2getactivefunctions-method"></a><span data-ttu-id="1b281-102">Метод ICorDebugThread2::GetActiveFunctions</span><span class="sxs-lookup"><span data-stu-id="1b281-102">ICorDebugThread2::GetActiveFunctions Method</span></span>

<span data-ttu-id="1b281-103">Возвращает сведения об активной функции в каждом кадре этого потока.</span><span class="sxs-lookup"><span data-stu-id="1b281-103">Gets information about the active function in each of this thread's frames.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b281-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b281-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b281-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b281-105">Parameters</span></span>  

 `cFunctions`  
 <span data-ttu-id="1b281-106">[in] Размер массива `pFunctions`.</span><span class="sxs-lookup"><span data-stu-id="1b281-106">[in] The size of the `pFunctions` array.</span></span>  
  
 `pcFunctions`  
 <span data-ttu-id="1b281-107">заполняет Указатель на число объектов, возвращаемых в `pFunctions` массиве.</span><span class="sxs-lookup"><span data-stu-id="1b281-107">[out] A pointer to the number of objects returned in the `pFunctions` array.</span></span> <span data-ttu-id="1b281-108">Число возвращаемых объектов будет равно числу управляемых кадров в стеке.</span><span class="sxs-lookup"><span data-stu-id="1b281-108">The number of objects returned will be equal to the number of managed frames on the stack.</span></span>  
  
 `pFunctions`  
 <span data-ttu-id="1b281-109">[вход, выход] Массив объектов COR_ACTIVE_FUNCTION, каждый из которых содержит сведения об активных функциях в кадрах этого потока.</span><span class="sxs-lookup"><span data-stu-id="1b281-109">[in, out] An array of COR_ACTIVE_FUNCTION objects, each of which contains information about the active functions in this thread's frames.</span></span>  
  
 <span data-ttu-id="1b281-110">Первый элемент будет использоваться для конечного фрейма и так далее — в корне стека.</span><span class="sxs-lookup"><span data-stu-id="1b281-110">The first element will be used for the leaf frame, and so on back to the root of the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b281-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="1b281-111">Remarks</span></span>  

 <span data-ttu-id="1b281-112">Если `pFunctions` для входных данных задано значение null, `GetActiveFunctions` функция возвращает только число функций в стеке.</span><span class="sxs-lookup"><span data-stu-id="1b281-112">If `pFunctions` is null on input, `GetActiveFunctions` returns only the number of functions that are on the stack.</span></span> <span data-ttu-id="1b281-113">То есть если `pFunctions` во входных данных параметр имеет значение null, `GetActiveFunctions` возвращает значение только в `pcFunctions` .</span><span class="sxs-lookup"><span data-stu-id="1b281-113">That is, If `pFunctions` is null on input, `GetActiveFunctions` returns a value only in `pcFunctions`.</span></span>  
  
 <span data-ttu-id="1b281-114">`GetActiveFunctions`Метод предназначен для оптимизации при получении тех же сведений из кадров в трассировке стека и включает только те кадры, для которых в полной трассировке стека был бы объект ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="1b281-114">The `GetActiveFunctions` method is intended as an optimization over getting the same information from frames in a stack trace, and includes only frames that would have had an ICorDebugILFrame object for them in the full stack trace.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b281-115">Требования</span><span class="sxs-lookup"><span data-stu-id="1b281-115">Requirements</span></span>  

 <span data-ttu-id="1b281-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b281-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b281-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b281-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b281-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b281-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b281-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b281-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
