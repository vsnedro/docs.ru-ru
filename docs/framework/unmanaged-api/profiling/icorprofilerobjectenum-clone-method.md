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
ms.openlocfilehash: df1d5881bccdb357b16c7f02cd090388e0f66273
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722808"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="9a455-102">Метод ICorProfilerObjectEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="9a455-102">ICorProfilerObjectEnum::Clone Method</span></span>

<span data-ttu-id="9a455-103">Получает указатель интерфейса на копию этого интерфейса [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="9a455-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a455-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9a455-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a455-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9a455-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="9a455-106">заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого `ICorProfilerObjectEnum` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="9a455-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="9a455-107">Копия хранит собственное состояние перечисления отдельно от этого экземпляра.</span><span class="sxs-lookup"><span data-stu-id="9a455-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="9a455-108">Однако начальная позиции курсора копии будет совпадать с текущей позицией курсора этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="9a455-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a455-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9a455-109">Requirements</span></span>  

 <span data-ttu-id="9a455-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a455-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a455-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9a455-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9a455-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a455-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a455-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a455-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a455-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9a455-114">See also</span></span>

- [<span data-ttu-id="9a455-115">Интерфейс ICorProfilerObjectEnum</span><span class="sxs-lookup"><span data-stu-id="9a455-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
