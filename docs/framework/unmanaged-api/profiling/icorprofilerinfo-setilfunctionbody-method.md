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
ms.openlocfilehash: 376b9fc637993f00722c48db7f51650e0a22d931
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720923"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="592a8-102">Метод ICorProfilerInfo::SetILFunctionBody</span><span class="sxs-lookup"><span data-stu-id="592a8-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>

<span data-ttu-id="592a8-103">Заменяет тело указанной функции в указанном модуле.</span><span class="sxs-lookup"><span data-stu-id="592a8-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="592a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="592a8-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="592a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="592a8-105">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="592a8-106">окне Идентификатор модуля, в котором находится функция.</span><span class="sxs-lookup"><span data-stu-id="592a8-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="592a8-107">окне Токен функции, для которой заменяется текст.</span><span class="sxs-lookup"><span data-stu-id="592a8-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="592a8-108">окне Новый заголовок для функции.</span><span class="sxs-lookup"><span data-stu-id="592a8-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="592a8-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="592a8-109">Remarks</span></span>  

 <span data-ttu-id="592a8-110">`SetILFunctionBody`Метод заменяет относительный виртуальный адрес функции в метаданных таким образом, чтобы он указывал на новый текст функции, и при необходимости корректирует все внутренние структуры данных.</span><span class="sxs-lookup"><span data-stu-id="592a8-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="592a8-111">`SetILFunctionBody`Метод можно вызывать только для тех функций, которые никогда не были скомпилированы JIT-компилятором.</span><span class="sxs-lookup"><span data-stu-id="592a8-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="592a8-112">Используйте метод [ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) , чтобы выделить пространство для нового метода, чтобы обеспечить совместимость буфера.</span><span class="sxs-lookup"><span data-stu-id="592a8-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="592a8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="592a8-113">Requirements</span></span>  

 <span data-ttu-id="592a8-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="592a8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="592a8-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="592a8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="592a8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="592a8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="592a8-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="592a8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="592a8-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="592a8-118">See also</span></span>

- [<span data-ttu-id="592a8-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="592a8-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
