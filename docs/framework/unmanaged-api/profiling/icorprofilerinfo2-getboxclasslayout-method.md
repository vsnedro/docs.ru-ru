---
title: Метод ICorProfilerInfo2::GetBoxClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: ff39a688132112e88438bc192d7c1ab61f169400
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727163"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="bde1b-102">Метод ICorProfilerInfo2::GetBoxClassLayout</span><span class="sxs-lookup"><span data-stu-id="bde1b-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>

<span data-ttu-id="bde1b-103">Возвращает сведения о расположении указанного типа значения при его упаковке.</span><span class="sxs-lookup"><span data-stu-id="bde1b-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bde1b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bde1b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bde1b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bde1b-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="bde1b-106">окне Идентификатор класса, который описывает упакованный тип значения.</span><span class="sxs-lookup"><span data-stu-id="bde1b-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="bde1b-107">заполняет Целое число, которое является смещением относительно указателя на идентификатор упакованного объекта для типа значения.</span><span class="sxs-lookup"><span data-stu-id="bde1b-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bde1b-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="bde1b-108">Remarks</span></span>  

 <span data-ttu-id="bde1b-109">`pBufferOffset`Значение — это расположение типа значения в поле.</span><span class="sxs-lookup"><span data-stu-id="bde1b-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="bde1b-110">После `pBufferOffset` применения к упакованному объекту можно использовать макет класса типа значения для интерпретации значения объекта.</span><span class="sxs-lookup"><span data-stu-id="bde1b-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bde1b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bde1b-111">Requirements</span></span>  

 <span data-ttu-id="bde1b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bde1b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bde1b-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bde1b-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bde1b-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bde1b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bde1b-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bde1b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bde1b-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bde1b-116">See also</span></span>

- [<span data-ttu-id="bde1b-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="bde1b-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="bde1b-118">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="bde1b-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
