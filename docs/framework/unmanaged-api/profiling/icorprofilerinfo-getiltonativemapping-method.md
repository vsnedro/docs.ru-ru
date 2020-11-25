---
title: Метод ICorProfilerInfo::GetILToNativeMapping
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILToNativeMapping
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILToNativeMapping
helpviewer_keywords:
- GetILToNativeMapping method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetILToNativeMapping method [.NET Framework profiling]
ms.assetid: 6a5431ef-22fb-4e53-bac5-703986297eb1
topic_type:
- apiref
ms.openlocfilehash: 1eb9b3af4c0e77fd1548de194d064eb85b86cdce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724160"
---
# <a name="icorprofilerinfogetiltonativemapping-method"></a><span data-ttu-id="2c46e-102">Метод ICorProfilerInfo::GetILToNativeMapping</span><span class="sxs-lookup"><span data-stu-id="2c46e-102">ICorProfilerInfo::GetILToNativeMapping Method</span></span>

<span data-ttu-id="2c46e-103">Получает сопоставление из смещений MSIL в собственные смещения для кода, содержащегося в указанной функции.</span><span class="sxs-lookup"><span data-stu-id="2c46e-103">Gets a map from Microsoft intermediate language (MSIL) offsets to native offsets for the code contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c46e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2c46e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c46e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2c46e-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="2c46e-106">[in] Идентификатор функции, которая содержит код.</span><span class="sxs-lookup"><span data-stu-id="2c46e-106">[in] The ID of the function that contains the code.</span></span>  
  
 `cMap`  
 <span data-ttu-id="2c46e-107">[in] Максимальный размер массива `map`.</span><span class="sxs-lookup"><span data-stu-id="2c46e-107">[in] The maximum size of the `map` array.</span></span>  
  
 `pcMap`  
 <span data-ttu-id="2c46e-108">[out] Общее количество доступных структур COR_DEBUG_IL_TO_NATIVE_MAP.</span><span class="sxs-lookup"><span data-stu-id="2c46e-108">[out] The total number of available COR_DEBUG_IL_TO_NATIVE_MAP structures.</span></span>  
  
 `map`  
 <span data-ttu-id="2c46e-109">[out] Массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`, каждая из которых задает смещения.</span><span class="sxs-lookup"><span data-stu-id="2c46e-109">[out] An array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures, each of which specifies the offsets.</span></span> <span data-ttu-id="2c46e-110">После возврата метода `GetILToNativeMapping` параметр `map` будет содержать все или некоторые из структур `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="2c46e-110">After the `GetILToNativeMapping` method returns, `map` will contain some or all of the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c46e-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="2c46e-111">Remarks</span></span>  

 <span data-ttu-id="2c46e-112">Метод `GetILToNativeMapping` возвращает массив структур `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="2c46e-112">The `GetILToNativeMapping` method returns an array of `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="2c46e-113">Чтобы убедиться, что определенные диапазоны машинных инструкций соответствуют специальным областям кода (например, прологу), в качестве поля в массиве можно `ilOffset` задать значение перечисления [кордебугилтонативемаппингтипес](../debugging/cordebugiltonativemappingtypes-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="2c46e-113">To convey that certain ranges of native instructions correspond to special regions of code (for example, the prolog), an entry in the array can have its `ilOffset` field set to a value of the [CorDebugIlToNativeMappingTypes](../debugging/cordebugiltonativemappingtypes-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="2c46e-114">После возврата метода `GetILToNativeMapping` необходимо убедиться, что буфер `map` был достаточно велик, чтобы вместить в себя все структуры `COR_DEBUG_IL_TO_NATIVE_MAP`.</span><span class="sxs-lookup"><span data-stu-id="2c46e-114">After `GetILToNativeMapping` returns, you must verify that the `map` buffer was large enough to contain all the `COR_DEBUG_IL_TO_NATIVE_MAP` structures.</span></span> <span data-ttu-id="2c46e-115">Для этого сравните значение параметра `cMap` со значением параметра `pcMap`.</span><span class="sxs-lookup"><span data-stu-id="2c46e-115">To do this, compare the value of `cMap` with the value of the `pcMap` parameter.</span></span> <span data-ttu-id="2c46e-116">Если значение `pcMap`, умноженное на размер структуры `COR_DEBUG_IL_TO_NATIVE_MAP`COR_PRF_CODE_INFO, больше значения `cMap`, выделите буфер `map` большего размера, обновите параметр `cMap`, задав новый, больший размер, и вызовите метод `GetILToNativeMapping` снова.</span><span class="sxs-lookup"><span data-stu-id="2c46e-116">If the `pcMap` value, when it is multiplied by the size of a `COR_DEBUG_IL_TO_NATIVE_MAP` structure, is larger than `cMap`, allocate a larger `map` buffer, update `cMap` with the new, larger size, and call `GetILToNativeMapping` again.</span></span>  
  
 <span data-ttu-id="2c46e-117">Кроме того, сначала можно вызвать метод `GetILToNativeMapping` с буфером `map` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="2c46e-117">Alternatively, you can first call `GetILToNativeMapping` with a zero-length `map` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="2c46e-118">Затем можно задать размер буфера равным значению, возвращенному в параметре `pcMap`, и вызвать метод `GetILToNativeMapping` снова.</span><span class="sxs-lookup"><span data-stu-id="2c46e-118">You can then set the buffer size to the value returned in `pcMap` and call `GetILToNativeMapping` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c46e-119">Требования</span><span class="sxs-lookup"><span data-stu-id="2c46e-119">Requirements</span></span>  

 <span data-ttu-id="2c46e-120">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c46e-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c46e-121">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2c46e-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2c46e-122">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c46e-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c46e-123">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c46e-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c46e-124">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2c46e-124">See also</span></span>

- [<span data-ttu-id="2c46e-125">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="2c46e-125">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="2c46e-126">Метод GetILToNativeMapping2</span><span class="sxs-lookup"><span data-stu-id="2c46e-126">GetILToNativeMapping2 Method</span></span>](icorprofilerinfo4-getiltonativemapping2-method.md)
- [<span data-ttu-id="2c46e-127">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="2c46e-127">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="2c46e-128">Профилирование</span><span class="sxs-lookup"><span data-stu-id="2c46e-128">Profiling</span></span>](index.md)
