---
title: Метод ICorProfilerInfo::SetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 462fc7222243f8cad4e1d03d1717eedace549836
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502942"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="86750-102">Метод ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="86750-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="86750-103">Заменяет тело указанной функции в указанном модуле.</span><span class="sxs-lookup"><span data-stu-id="86750-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86750-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="86750-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86750-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="86750-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="86750-106">окне Идентификатор модуля, в котором находится функция.</span><span class="sxs-lookup"><span data-stu-id="86750-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="86750-107">окне Токен функции, для которой заменяется текст.</span><span class="sxs-lookup"><span data-stu-id="86750-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="86750-108">окне Новый заголовок для функции.</span><span class="sxs-lookup"><span data-stu-id="86750-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86750-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="86750-109">Remarks</span></span>  
 <span data-ttu-id="86750-110">`SetILFunctionBody`Метод заменяет относительный виртуальный адрес функции в метаданных таким образом, чтобы он указывал на новый текст функции, и при необходимости корректирует все внутренние структуры данных.</span><span class="sxs-lookup"><span data-stu-id="86750-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="86750-111">`SetILFunctionBody`Метод можно вызывать только для тех функций, которые никогда не были скомпилированы JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="86750-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="86750-112">Используйте метод [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) , чтобы выделить пространство для нового метода, чтобы обеспечить совместимость буфера.</span><span class="sxs-lookup"><span data-stu-id="86750-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86750-113">Требования</span><span class="sxs-lookup"><span data-stu-id="86750-113">Requirements</span></span>  
 <span data-ttu-id="86750-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86750-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86750-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86750-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86750-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86750-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86750-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86750-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86750-118">См. также</span><span class="sxs-lookup"><span data-stu-id="86750-118">See also</span></span>

- [<span data-ttu-id="86750-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="86750-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
