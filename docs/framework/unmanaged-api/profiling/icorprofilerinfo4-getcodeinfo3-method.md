---
title: Метод ICorProfilerInfo4::GetCodeInfo3
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetCodeInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetCodeInfo3
helpviewer_keywords:
- GetCodeInfo3 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetCodeInfo3 method [.NET Framework profiling]
ms.assetid: bb8c105e-4d9a-4684-8c05-ed6909cc1b8c
topic_type:
- apiref
ms.openlocfilehash: 54e522aaaf23ae81b96b6be7168a9a13f28a16d2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496143"
---
# <a name="icorprofilerinfo4getcodeinfo3-method"></a><span data-ttu-id="7e160-102">Метод ICorProfilerInfo4::GetCodeInfo3</span><span class="sxs-lookup"><span data-stu-id="7e160-102">ICorProfilerInfo4::GetCodeInfo3 Method</span></span>
<span data-ttu-id="7e160-103">Получает экстенты машинного кода, связанного с перекомпилированной с помощью JIT-компилятора версией указанной функции.</span><span class="sxs-lookup"><span data-stu-id="7e160-103">Gets the extents of native code associated with the JIT-recompiled version of the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e160-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7e160-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodeInfo3(  
    [in]  FunctionID functionID,  
    [in]  ReJITID reJitId,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e160-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7e160-105">Parameters</span></span>  
 `functionID`  
 <span data-ttu-id="7e160-106">[in] Идентификатор функции, с которым связан машинный код.</span><span class="sxs-lookup"><span data-stu-id="7e160-106">[in] The ID of the function with which the native code is associated.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="7e160-107">[in] Идентификатор функции, перекомпилированной с помощью JIT-компилятора.</span><span class="sxs-lookup"><span data-stu-id="7e160-107">[in] The identity of the JIT-recompiled function.</span></span>  
  
 `cCodeInfos`  
 <span data-ttu-id="7e160-108">[in] Размер массива `codeInfos`.</span><span class="sxs-lookup"><span data-stu-id="7e160-108">[in] The size of the `codeInfos` array.</span></span>  
  
 `pcCodeInfos`  
 <span data-ttu-id="7e160-109">заполняет Указатель на общее число доступных структур [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="7e160-109">[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>  
  
 `codeInfos`  
 <span data-ttu-id="7e160-110">[out] Буфер, предоставляемый вызывающим объектом.</span><span class="sxs-lookup"><span data-stu-id="7e160-110">[out] A caller-provided buffer.</span></span> <span data-ttu-id="7e160-111">После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.</span><span class="sxs-lookup"><span data-stu-id="7e160-111">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7e160-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="7e160-112">Remarks</span></span>  
 <span data-ttu-id="7e160-113">`GetCodeInfo3`Метод аналогичен [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md), за исключением того, что он получает JIT-перекомпилированный идентификатор функции, которая содержит указанный IP-адрес.</span><span class="sxs-lookup"><span data-stu-id="7e160-113">The `GetCodeInfo3` method is similar to [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md), except that it will get the JIT-recompiled ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e160-114">`GetCodeInfo3`может запустить сборку мусора, в то время как [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) не будет.</span><span class="sxs-lookup"><span data-stu-id="7e160-114">`GetCodeInfo3` can trigger a garbage collection, whereas [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) will not.</span></span> <span data-ttu-id="7e160-115">Дополнительные сведения см. в [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span><span class="sxs-lookup"><span data-stu-id="7e160-115">For more information, see the [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](corprof-e-unsupported-call-sequence-hresult.md) HRESULT.</span></span>  
  
 <span data-ttu-id="7e160-116">Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).</span><span class="sxs-lookup"><span data-stu-id="7e160-116">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>  
  
 <span data-ttu-id="7e160-117">После `GetCodeInfo3` возврата необходимо убедиться, что `codeInfos` буфер достаточно велик, чтобы вместить все структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="7e160-117">After `GetCodeInfo3` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="7e160-118">Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="7e160-118">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="7e160-119">При `cCodeInfos` делении на размер структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) меньше `pcCodeInfos` , выделяет буфер большего размера `codeInfos` , обновляет `cCodeInfos` новый, больший размер и вызывается `GetCodeInfo3` снова.</span><span class="sxs-lookup"><span data-stu-id="7e160-119">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo3` again.</span></span>  
  
 <span data-ttu-id="7e160-120">Кроме того, сначала можно вызвать метод `GetCodeInfo3` с буфером `codeInfos` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="7e160-120">Alternatively, you can first call `GetCodeInfo3` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="7e160-121">Затем можно присвоить `codeInfos` Размер буфера значению, возвращенному в `pcCodeInfos` , умноженному на размер структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) и вызывать `GetCodeInfo3` повторно.</span><span class="sxs-lookup"><span data-stu-id="7e160-121">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo3` again.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7e160-122">Требования</span><span class="sxs-lookup"><span data-stu-id="7e160-122">Requirements</span></span>  
 <span data-ttu-id="7e160-123">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e160-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e160-124">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7e160-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7e160-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7e160-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7e160-126">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e160-126">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e160-127">См. также</span><span class="sxs-lookup"><span data-stu-id="7e160-127">See also</span></span>

- [<span data-ttu-id="7e160-128">Метод GetCodeInfo2</span><span class="sxs-lookup"><span data-stu-id="7e160-128">GetCodeInfo2 Method</span></span>](icorprofilerinfo2-getcodeinfo2-method.md)
- [<span data-ttu-id="7e160-129">Интерфейс ICorProfilerInfo4</span><span class="sxs-lookup"><span data-stu-id="7e160-129">ICorProfilerInfo4 Interface</span></span>](icorprofilerinfo4-interface.md)
- [<span data-ttu-id="7e160-130">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="7e160-130">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="7e160-131">Профилирование</span><span class="sxs-lookup"><span data-stu-id="7e160-131">Profiling</span></span>](index.md)
