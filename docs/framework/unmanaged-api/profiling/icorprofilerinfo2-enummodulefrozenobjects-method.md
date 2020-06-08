---
title: Метод ICorProfilerInfo2::EnumModuleFrozenObjects
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: 1fe44f8f84c079e920c8c82fb9d52d1980d3b852
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497209"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="c990e-102">Метод ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="c990e-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="c990e-103">Возвращает перечислитель, позволяющий выполнять итерацию зафиксированных объектов в указанном модуле. Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="c990e-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c990e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c990e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c990e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c990e-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="c990e-106">окне Идентификатор модуля, содержащего зафиксированные объекты для перечисления.</span><span class="sxs-lookup"><span data-stu-id="c990e-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="c990e-107">заполняет Указатель на адрес интерфейса [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , который перечисляет зафиксированные объекты.</span><span class="sxs-lookup"><span data-stu-id="c990e-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c990e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c990e-108">Requirements</span></span>  
 <span data-ttu-id="c990e-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c990e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c990e-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c990e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c990e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c990e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c990e-112">**.NET Framework версии:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0</span><span class="sxs-lookup"><span data-stu-id="c990e-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c990e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c990e-113">See also</span></span>

- [<span data-ttu-id="c990e-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="c990e-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c990e-115">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="c990e-115">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
