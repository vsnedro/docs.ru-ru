---
title: Метод ICorProfilerObjectEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.GetCount
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::GetCount
helpviewer_keywords:
- ICorProfilerObjectEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 166b0761-ed80-4ccd-9973-dc20e61bf8fa
topic_type:
- apiref
ms.openlocfilehash: 4c867a9e263f022fc6f8d90a883562e2560ad1b2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494661"
---
# <a name="icorprofilerobjectenumgetcount-method"></a><span data-ttu-id="c2e95-102">Метод ICorProfilerObjectEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="c2e95-102">ICorProfilerObjectEnum::GetCount Method</span></span>
<span data-ttu-id="c2e95-103">Возвращает общее число замороженных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c2e95-103">Gets the total number of frozen objects in the collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e95-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2e95-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2e95-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2e95-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="c2e95-106">заполняет Указатель на число замороженных объектов в коллекции.</span><span class="sxs-lookup"><span data-stu-id="c2e95-106">[out] A pointer to the number of frozen objects in the collection.</span></span>  
  
 <span data-ttu-id="c2e95-107">Этот метод всегда будет возвращать ноль в .NET Framework версии 3,5 с пакетом обновления 1 (SP1) и более поздних версиях.</span><span class="sxs-lookup"><span data-stu-id="c2e95-107">This method will always return zero in the .NET Framework version 3.5 Service Pack 1 (SP1) and later versions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2e95-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c2e95-108">Requirements</span></span>  
 <span data-ttu-id="c2e95-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2e95-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e95-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2e95-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2e95-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2e95-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2e95-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2e95-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e95-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c2e95-113">See also</span></span>

- [<span data-ttu-id="c2e95-114">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="c2e95-114">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
