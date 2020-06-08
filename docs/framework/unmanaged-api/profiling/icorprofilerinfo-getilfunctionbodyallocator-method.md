---
title: Метод ICorProfilerInfo::GetILFunctionBodyAllocator
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBodyAllocator
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBodyAllocator
helpviewer_keywords:
- GetILFunctionBodyAllocator method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBodyAllocator method [.NET Framework profiling]
ms.assetid: 5da1bf3d-dddf-4892-b266-578ee54d570b
topic_type:
- apiref
ms.openlocfilehash: 967f38add9ae5996c6ac33388203b55161a84e39
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498275"
---
# <a name="icorprofilerinfogetilfunctionbodyallocator-method"></a><span data-ttu-id="5aa34-102">Метод ICorProfilerInfo::GetILFunctionBodyAllocator</span><span class="sxs-lookup"><span data-stu-id="5aa34-102">ICorProfilerInfo::GetILFunctionBodyAllocator Method</span></span>
<span data-ttu-id="5aa34-103">Возвращает интерфейс, предоставляющий метод для выделения памяти, используемой для перекачки тела метода в коде на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="5aa34-103">Gets an interface that provides a method to allocate memory to be used for swapping out the body of a method in Microsoft intermediate language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa34-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5aa34-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILFunctionBodyAllocator(  
    [in]  ModuleID      moduleId,  
    [out] IMethodMalloc **ppMalloc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aa34-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5aa34-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="5aa34-106">окне Идентификатор модуля, в котором находится метод.</span><span class="sxs-lookup"><span data-stu-id="5aa34-106">[in] The ID of the module in which the method resides.</span></span>  
  
 `ppMalloc`  
 <span data-ttu-id="5aa34-107">заполняет Указатель на интерфейс [IMethodMalloc](imethodmalloc-interface.md) , предоставляющий метод для выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="5aa34-107">[out] A pointer to an [IMethodMalloc](imethodmalloc-interface.md) interface that provides a method to allocate the memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aa34-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="5aa34-108">Remarks</span></span>  
 <span data-ttu-id="5aa34-109">Тело метода в коде MSIL должен располагаться как относительный виртуальный адрес (RVA) относительно загруженного модуля. Это означает, что он следует за модулем в пределах 4 ГБ.</span><span class="sxs-lookup"><span data-stu-id="5aa34-109">A method body in MSIL code must be located as a relative virtual address (RVA), relative to the loaded module, which means that it follows the module within 4 GB.</span></span> <span data-ttu-id="5aa34-110">Чтобы упростить средство для замены тела метода, `GetILFunctionBodyAllocator` метод обеспечивает выделение памяти в пределах этого диапазона.</span><span class="sxs-lookup"><span data-stu-id="5aa34-110">To make it easier for a tool to swap out the body of a method, the `GetILFunctionBodyAllocator` method ensures that memory is allocated within that range.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aa34-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5aa34-111">Requirements</span></span>  
 <span data-ttu-id="5aa34-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5aa34-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aa34-113">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5aa34-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5aa34-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5aa34-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5aa34-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aa34-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa34-116">См. также</span><span class="sxs-lookup"><span data-stu-id="5aa34-116">See also</span></span>

- [<span data-ttu-id="5aa34-117">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5aa34-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
