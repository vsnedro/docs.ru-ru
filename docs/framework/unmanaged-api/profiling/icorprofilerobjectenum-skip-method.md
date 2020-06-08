---
title: Метод ICorProfilerObjectEnum::Skip
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Skip
helpviewer_keywords:
- ICorProfilerObjectEnum::Skip method [.NET Framework profiling]
- Skip method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: f8e498f8-f93a-4b82-bd22-55bdbf5e8d45
topic_type:
- apiref
ms.openlocfilehash: 2248f99b76aaabff4bd3dc78b6e777a95692bb9c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494531"
---
# <a name="icorprofilerobjectenumskip-method"></a><span data-ttu-id="1d74f-102">Метод ICorProfilerObjectEnum::Skip</span><span class="sxs-lookup"><span data-stu-id="1d74f-102">ICorProfilerObjectEnum::Skip Method</span></span>
<span data-ttu-id="1d74f-103">Перемещает курсор этого перечислителя из текущей позиции, чтобы было пропущено указанное число элементов.</span><span class="sxs-lookup"><span data-stu-id="1d74f-103">Advances the cursor of this enumerator from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d74f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1d74f-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d74f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1d74f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1d74f-106">окне Число пропущенных элементов.</span><span class="sxs-lookup"><span data-stu-id="1d74f-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1d74f-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1d74f-107">Remarks</span></span>  
 <span data-ttu-id="1d74f-108">Новая позиции курсора перечислителя: (Текущая позиции) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="1d74f-108">The new position of this enumerator's cursor is: (current position) + `celt` .</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d74f-109">Требования</span><span class="sxs-lookup"><span data-stu-id="1d74f-109">Requirements</span></span>  
 <span data-ttu-id="1d74f-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d74f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d74f-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1d74f-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1d74f-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1d74f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1d74f-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d74f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d74f-114">См. также</span><span class="sxs-lookup"><span data-stu-id="1d74f-114">See also</span></span>

- [<span data-ttu-id="1d74f-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="1d74f-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
