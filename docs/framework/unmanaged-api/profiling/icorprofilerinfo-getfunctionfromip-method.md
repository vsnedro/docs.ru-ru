---
title: Метод ICorProfilerInfo::GetFunctionFromIP
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 339c5db1610a3cf087085ce19fc663436d9c4ec1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498314"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="a607e-102">Метод ICorProfilerInfo::GetFunctionFromIP</span><span class="sxs-lookup"><span data-stu-id="a607e-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="a607e-103">Сопоставляет указатель инструкции управляемого кода с `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="a607e-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a607e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a607e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a607e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a607e-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="a607e-106">\[in] указатель инструкций в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="a607e-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="a607e-107">\[out] возвращаемый идентификатор функции.</span><span class="sxs-lookup"><span data-stu-id="a607e-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="a607e-108">Требования</span><span class="sxs-lookup"><span data-stu-id="a607e-108">Requirements</span></span>  
 <span data-ttu-id="a607e-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a607e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a607e-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a607e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a607e-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a607e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a607e-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a607e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a607e-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a607e-113">See also</span></span>

- [<span data-ttu-id="a607e-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="a607e-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
