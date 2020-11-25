---
title: Метод ICorProfilerInfo::GetObjectSize
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetObjectSize
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetObjectSize
helpviewer_keywords:
- GetObjectSize method [.NET Framework profiling]
- ICorProfilerInfo::GetObjectSize method [.NET Framework profiling]
ms.assetid: 9f02e763-73f7-42cb-a41c-f78499d9482c
topic_type:
- apiref
ms.openlocfilehash: 4abcf9f4575b32dd125fd8a00783043900993c3e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724108"
---
# <a name="icorprofilerinfogetobjectsize-method"></a><span data-ttu-id="44a81-102">Метод ICorProfilerInfo::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="44a81-102">ICorProfilerInfo::GetObjectSize Method</span></span>

<span data-ttu-id="44a81-103">Возвращает размер указанного объекта.</span><span class="sxs-lookup"><span data-stu-id="44a81-103">Gets the size of a specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44a81-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44a81-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
    [in]  ObjectID objectId,  
    [out] ULONG  *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44a81-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="44a81-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="44a81-106">окне Идентификатор объекта.</span><span class="sxs-lookup"><span data-stu-id="44a81-106">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="44a81-107">заполняет Указатель на размер объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="44a81-107">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44a81-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="44a81-108">Remarks</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="44a81-109">Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="44a81-109">This method is obsolete.</span></span> <span data-ttu-id="44a81-110">Он Возвращает COR_E_OVERFLOW для объектов размером более 4 ГБ на 64-разрядных платформах.</span><span class="sxs-lookup"><span data-stu-id="44a81-110">It returns COR_E_OVERFLOW for objects greater than 4GB on 64-bit platforms.</span></span> <span data-ttu-id="44a81-111">Используйте вместо этого метод  [метод icorprofilerinfo4:: GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="44a81-111">Use the  [ICorProfilerInfo4::GetObjectSize2](icorprofilerinfo4-getobjectsize2-method.md) method instead.</span></span>  
  
 <span data-ttu-id="44a81-112">Различные объекты одних и тех же типов часто имеют одинаковый размер.</span><span class="sxs-lookup"><span data-stu-id="44a81-112">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="44a81-113">Однако некоторые типы, такие как массивы или строки, могут иметь разные размеры для каждого объекта.</span><span class="sxs-lookup"><span data-stu-id="44a81-113">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
 <span data-ttu-id="44a81-114">Размер, возвращаемый `GetObjectSize` методом, не включает заполнение выравнивания, которое может появиться после того, как объект находится в куче сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="44a81-114">The size returned by the `GetObjectSize` method does not include any alignment padding that may appear after the object is on the garbage collection heap.</span></span> <span data-ttu-id="44a81-115">При использовании `GetObjectSize` метода для перехода от объекта к объекту в куче сборки мусора при необходимости добавьте заполнение выравнивания вручную.</span><span class="sxs-lookup"><span data-stu-id="44a81-115">If you use the `GetObjectSize` method to advance from object to object on the garbage collection heap, add alignment padding manually, as necessary.</span></span>  
  
- <span data-ttu-id="44a81-116">В 32-разрядных Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1 и COR_PRF_GC_GEN_2 использовать 4-байтовый выравнивание, а COR_PRF_GC_LARGE_OBJECT_HEAP использует 8-байтное выравнивание.</span><span class="sxs-lookup"><span data-stu-id="44a81-116">On 32-bit Windows, COR_PRF_GC_GEN_0, COR_PRF_GC_GEN_1, and COR_PRF_GC_GEN_2 use 4-byte alignment, and COR_PRF_GC_LARGE_OBJECT_HEAP uses 8-byte alignment.</span></span>  
  
- <span data-ttu-id="44a81-117">В 64-разрядной Windows выравнивание всегда равно 8 байтам.</span><span class="sxs-lookup"><span data-stu-id="44a81-117">On 64-bit Windows, the alignment is always 8 bytes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44a81-118">Требования</span><span class="sxs-lookup"><span data-stu-id="44a81-118">Requirements</span></span>  

 <span data-ttu-id="44a81-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44a81-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44a81-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="44a81-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="44a81-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44a81-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44a81-122">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44a81-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44a81-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="44a81-123">See also</span></span>

- [<span data-ttu-id="44a81-124">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="44a81-124">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
