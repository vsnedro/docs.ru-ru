---
title: Метод ICorProfilerThreadEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
ms.openlocfilehash: de2584b56701f4cffb6a108a5872641ec40e5762
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702528"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="13761-102">Метод ICorProfilerThreadEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="13761-102">ICorProfilerThreadEnum::Clone Method</span></span>

<span data-ttu-id="13761-103">Получает указатель интерфейса на копию этого интерфейса [икорпрофилерсреаденум](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="13761-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13761-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13761-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13761-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13761-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="13761-106">заполняет Указатель на указатель интерфейса, который, в свою очередь, указывает на копию этого интерфейса [икорпрофилерсреаденум](icorprofilerthreadenum-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="13761-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="13761-107">Копия перечислителя поддерживает собственное состояние перечисления отдельно от этого перечислителя.</span><span class="sxs-lookup"><span data-stu-id="13761-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="13761-108">Однако начальная координата курсора копирования совпадает с текущей позицией курсора в перечислителе.</span><span class="sxs-lookup"><span data-stu-id="13761-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13761-109">Требования</span><span class="sxs-lookup"><span data-stu-id="13761-109">Requirements</span></span>  

 <span data-ttu-id="13761-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13761-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13761-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="13761-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="13761-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13761-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13761-113">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13761-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13761-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="13761-114">See also</span></span>

- [<span data-ttu-id="13761-115">икорпрофилерсреаденум</span><span class="sxs-lookup"><span data-stu-id="13761-115">ICorProfilerThreadEnum</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="13761-116">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="13761-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
