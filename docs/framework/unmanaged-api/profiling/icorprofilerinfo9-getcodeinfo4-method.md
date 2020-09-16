---
title: ICorProfilerInfo9::GetCodeInfo4
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetCodeInfo4
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: ecaff179378eb417393c0a0d17d0a00d3b99e5a4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90541302"
---
# <a name="icorprofilerinfo9getcodeinfo4-method"></a><span data-ttu-id="805ec-102">Метод ICorProfilerInfo9:: GetCodeInfo4</span><span class="sxs-lookup"><span data-stu-id="805ec-102">ICorProfilerInfo9::GetCodeInfo4 Method</span></span>

<span data-ttu-id="805ec-103">При наличии начального адреса машинного кода возвращает блоки виртуальной памяти, в которых хранится этот код.</span><span class="sxs-lookup"><span data-stu-id="805ec-103">Given the native code start address, returns the blocks of virtual memory that store this code.</span></span>

## <a name="syntax"></a><span data-ttu-id="805ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="805ec-104">Syntax</span></span>

```cpp
HRESULT GetCodeInfo4( [in]  UINT_PTR pNativeCodeStartAddress,
                      [in]  ULONG32 cCodeInfos,
                      [out] ULONG32* pcCodeInfos,
                      [out] COR_PRF_CODE_INFO codeInfos[]);
```

## <a name="parameters"></a><span data-ttu-id="805ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="805ec-105">Parameters</span></span>

- `pNativeCodeStartAddress`

  <span data-ttu-id="805ec-106">\[in] указатель на начало собственной функции.</span><span class="sxs-lookup"><span data-stu-id="805ec-106">\[in] A pointer to the start of a native function.</span></span>

- `cCodeInfos`

  <span data-ttu-id="805ec-107">\[in] размер `codeInfos` массива.</span><span class="sxs-lookup"><span data-stu-id="805ec-107">\[in] The size of the `codeInfos` array.</span></span>

- `pcCodeInfos`

  <span data-ttu-id="805ec-108">\[out] указатель на общее число доступных структур [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="805ec-108">\[out] A pointer to the total number of [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures available.</span></span>

- `codeInfos`

  <span data-ttu-id="805ec-109">\[out] буфер, предоставленный вызывающей стороной.</span><span class="sxs-lookup"><span data-stu-id="805ec-109">\[out] A caller-provided buffer.</span></span> <span data-ttu-id="805ec-110">После возврата метода он содержит массив структур `COR_PRF_CODE_INFO`, каждая из которых описывает блок машинного кода.</span><span class="sxs-lookup"><span data-stu-id="805ec-110">After the method returns, it contains an array of `COR_PRF_CODE_INFO` structures, each of which describes a block of native code.</span></span>

## <a name="remarks"></a><span data-ttu-id="805ec-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="805ec-111">Remarks</span></span>

<span data-ttu-id="805ec-112">`GetCodeInfo4`Метод аналогичен [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), за исключением того, что он может искать информацию о коде для различных версий метода.</span><span class="sxs-lookup"><span data-stu-id="805ec-112">The `GetCodeInfo4` method is similar to [GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md), except that it can look up code information for different native versions of a method.</span></span>

> [!NOTE]
> <span data-ttu-id="805ec-113">`GetCodeInfo4` может запустить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="805ec-113">`GetCodeInfo4` can trigger a garbage collection.</span></span>

<span data-ttu-id="805ec-114">Расширения сортируются в порядке возрастания смещения общих промежуточного языка (CIL).</span><span class="sxs-lookup"><span data-stu-id="805ec-114">The extents are sorted in order of increasing Common Intermediate Language (CIL) offset.</span></span>

<span data-ttu-id="805ec-115">После `GetCodeInfo4` возврата необходимо убедиться, что `codeInfos` буфер достаточно велик, чтобы вместить все структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) .</span><span class="sxs-lookup"><span data-stu-id="805ec-115">After `GetCodeInfo4` returns, you must verify that the `codeInfos` buffer was large enough to contain all the [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structures.</span></span> <span data-ttu-id="805ec-116">Для этого сравните значение параметра `cCodeInfos` со значением параметра `cchName`.</span><span class="sxs-lookup"><span data-stu-id="805ec-116">To do this, compare the value of `cCodeInfos` with the value of the `cchName` parameter.</span></span> <span data-ttu-id="805ec-117">При `cCodeInfos` делении на размер структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) меньше `pcCodeInfos` , выделяет буфер большего размера `codeInfos` , обновляет `cCodeInfos` новый, больший размер и вызывается `GetCodeInfo4` снова.</span><span class="sxs-lookup"><span data-stu-id="805ec-117">If `cCodeInfos` divided by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure is smaller than `pcCodeInfos`, allocate a larger `codeInfos` buffer, update `cCodeInfos` with the new, larger size, and call `GetCodeInfo4` again.</span></span>

<span data-ttu-id="805ec-118">Кроме того, сначала можно вызвать метод `GetCodeInfo4` с буфером `codeInfos` нулевой длины для получения правильного размера буфера.</span><span class="sxs-lookup"><span data-stu-id="805ec-118">Alternatively, you can first call `GetCodeInfo4` with a zero-length `codeInfos` buffer to obtain the correct buffer size.</span></span> <span data-ttu-id="805ec-119">Затем можно присвоить `codeInfos` Размер буфера значению, возвращенному в `pcCodeInfos` , умноженному на размер структуры [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) и вызывать `GetCodeInfo4` повторно.</span><span class="sxs-lookup"><span data-stu-id="805ec-119">You can then set the `codeInfos` buffer size to the value returned in `pcCodeInfos`, multiplied by the size of a [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) structure, and call `GetCodeInfo4` again.</span></span>

## <a name="requirements"></a><span data-ttu-id="805ec-120">Требования</span><span class="sxs-lookup"><span data-stu-id="805ec-120">Requirements</span></span>

<span data-ttu-id="805ec-121">**Платформы:** См. раздел [Поддерживаемые операционные системы .NET Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="805ec-121">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="805ec-122">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="805ec-122">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="805ec-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="805ec-123">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="805ec-124">**Версии .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="805ec-124">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="805ec-125">См. также</span><span class="sxs-lookup"><span data-stu-id="805ec-125">See also</span></span>

- [<span data-ttu-id="805ec-126">Интерфейс ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="805ec-126">ICorProfilerInfo9 Interface</span></span>](ICorProfilerInfo9-interface.md)
