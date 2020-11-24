---
title: 'Метод ICorDebugVariableHomeEnum:: Next'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
ms.openlocfilehash: 4ef4ed19033b0857b9970ee8103bbd92f383898c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679537"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="14031-102">Метод ICorDebugVariableHomeEnum:: Next</span><span class="sxs-lookup"><span data-stu-id="14031-102">ICorDebugVariableHomeEnum::Next Method</span></span>

<span data-ttu-id="14031-103">Возвращает указанное число экземпляров [ICorDebugVariableHome](icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.</span><span class="sxs-lookup"><span data-stu-id="14031-103">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14031-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14031-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14031-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="14031-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="14031-106">[in] Количество объектов, которые должны быть получены.</span><span class="sxs-lookup"><span data-stu-id="14031-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="14031-107">Массив указателей, каждый из которых указывает на объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) , предоставляющий сведения о локальной переменной или аргументе функции.</span><span class="sxs-lookup"><span data-stu-id="14031-107">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="14031-108">заполняет Число экземпляров, фактически возвращаемых в объектах.</span><span class="sxs-lookup"><span data-stu-id="14031-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14031-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="14031-109">Return Value</span></span>  

 <span data-ttu-id="14031-110">Метод возвращает следующие значения.</span><span class="sxs-lookup"><span data-stu-id="14031-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="14031-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14031-111">HRESULT</span></span>|<span data-ttu-id="14031-112">Описание</span><span class="sxs-lookup"><span data-stu-id="14031-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="14031-113">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="14031-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="14031-114">Фактическое число получаемых экземпляров, как показано в `pceltFetched` , меньше числа запрошенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="14031-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="14031-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="14031-115">Remarks</span></span>  

 <span data-ttu-id="14031-116">Метод [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) извлекает максимум  `celt` объектов, начиная с текущей позиции перечислителя.</span><span class="sxs-lookup"><span data-stu-id="14031-116">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="14031-117">При возврате из метода `pceltFetched` содержит фактическое число извлеченных объектов.</span><span class="sxs-lookup"><span data-stu-id="14031-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14031-118">Требования</span><span class="sxs-lookup"><span data-stu-id="14031-118">Requirements</span></span>  

 <span data-ttu-id="14031-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14031-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14031-120">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="14031-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="14031-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14031-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14031-122">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14031-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14031-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="14031-123">See also</span></span>

- [<span data-ttu-id="14031-124">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="14031-124">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="14031-125">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="14031-125">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
