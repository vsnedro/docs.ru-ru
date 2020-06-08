---
title: Метод ICorProfilerInfo::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromToken
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromToken
helpviewer_keywords:
- ICorProfilerInfo::GetFunctionFromToken method [.NET Framework profiling]
- GetFunctionFromToken method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 0eed759f-cce8-405d-88dc-9ee293a38928
topic_type:
- apiref
ms.openlocfilehash: 18c3b6e840ec1f6cb1481c8d752e6399dcdae077
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498145"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="e4d3b-102">Метод ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="e4d3b-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>
<span data-ttu-id="e4d3b-103">Возвращает идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-103">Gets the ID of a function.</span></span> <span data-ttu-id="e4d3b-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e4d3b-105">Используйте вместо этого метод [ICorProfilerInfo2:: жетфунктионфромтокенандтипеаргс](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e4d3b-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d3b-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4d3b-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="e4d3b-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4d3b-107">Remarks</span></span>  
 <span data-ttu-id="e4d3b-108">`GetFunctionFromToken`Метод не будет работать для универсальных функций или функций в универсальных типах. Теперь он устарел.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="e4d3b-109">Используется `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` для всех функций.</span><span class="sxs-lookup"><span data-stu-id="e4d3b-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d3b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e4d3b-110">Requirements</span></span>  
 <span data-ttu-id="e4d3b-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4d3b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d3b-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4d3b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4d3b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4d3b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4d3b-114">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="e4d3b-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d3b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e4d3b-115">See also</span></span>

- [<span data-ttu-id="e4d3b-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e4d3b-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
