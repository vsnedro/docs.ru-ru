---
title: Метод ICorProfilerObjectEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: a2a54c32c0713b4b69d8f2a0272687cbe9420610
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494778"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="5536e-102">Метод ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="5536e-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="5536e-103">Получает указатель интерфейса на копию этого интерфейса [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="5536e-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5536e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5536e-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5536e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5536e-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="5536e-106">заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого `ICorProfilerObjectEnum` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="5536e-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="5536e-107">Копия хранит собственное состояние перечисления отдельно от этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="5536e-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="5536e-108">Однако начальная позиции курсора копии будет совпадать с текущей позицией курсора этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="5536e-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5536e-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5536e-109">Requirements</span></span>  
 <span data-ttu-id="5536e-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5536e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5536e-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5536e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5536e-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5536e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5536e-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5536e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5536e-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5536e-114">See also</span></span>

- [<span data-ttu-id="5536e-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="5536e-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
