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
ms.openlocfilehash: 9c7f01d2e462ad1cb0532be6f369c3118a4deb6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722496"
---
# <a name="icorprofilerinfogetfunctionfromtoken-method"></a><span data-ttu-id="a73f0-102">Метод ICorProfilerInfo::GetFunctionFromToken</span><span class="sxs-lookup"><span data-stu-id="a73f0-102">ICorProfilerInfo::GetFunctionFromToken Method</span></span>

<span data-ttu-id="a73f0-103">Возвращает идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="a73f0-103">Gets the ID of a function.</span></span> <span data-ttu-id="a73f0-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="a73f0-104">This method is obsolete in the .NET Framework version 2.0.</span></span> <span data-ttu-id="a73f0-105">Используйте вместо этого метод [ICorProfilerInfo2:: жетфунктионфромтокенандтипеаргс](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a73f0-105">Use the [ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a73f0-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a73f0-106">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in]  ModuleID   moduleId,  
    [in]  mdToken    token,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="remarks"></a><span data-ttu-id="a73f0-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="a73f0-107">Remarks</span></span>  

 <span data-ttu-id="a73f0-108">`GetFunctionFromToken`Метод не будет работать для универсальных функций или функций в универсальных типах. Теперь он устарел.</span><span class="sxs-lookup"><span data-stu-id="a73f0-108">The `GetFunctionFromToken` method will not work for generic functions or functions in generic types; it is now obsolete.</span></span> <span data-ttu-id="a73f0-109">Используется `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` для всех функций.</span><span class="sxs-lookup"><span data-stu-id="a73f0-109">Use `ICorProfilerInfo2::GetFunctionFromTokenAndTypeArgs` for all functions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a73f0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a73f0-110">Requirements</span></span>  

 <span data-ttu-id="a73f0-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a73f0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a73f0-112">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a73f0-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a73f0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a73f0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a73f0-114">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="a73f0-114">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a73f0-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a73f0-115">See also</span></span>

- [<span data-ttu-id="a73f0-116">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a73f0-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
