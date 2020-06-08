---
title: Интерфейс IMethodMalloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: 12b97b28383eb7c39f20ee0e88f55d48e60ad956
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494115"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="08e98-102">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="08e98-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="08e98-103">Предоставляет метод для выделения памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="08e98-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08e98-104">`IMethodMalloc`Интерфейс — это простой механизм выделения памяти.</span><span class="sxs-lookup"><span data-stu-id="08e98-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="08e98-105">Она позволяет выделить память, но не освобождает ее.</span><span class="sxs-lookup"><span data-stu-id="08e98-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="08e98-106">Методы</span><span class="sxs-lookup"><span data-stu-id="08e98-106">Methods</span></span>  
  
|<span data-ttu-id="08e98-107">Метод</span><span class="sxs-lookup"><span data-stu-id="08e98-107">Method</span></span>|<span data-ttu-id="08e98-108">Описание</span><span class="sxs-lookup"><span data-stu-id="08e98-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="08e98-109">Метод Alloc</span><span class="sxs-lookup"><span data-stu-id="08e98-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="08e98-110">Пытается выделить указанный объем памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="08e98-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08e98-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="08e98-111">Remarks</span></span>  
 <span data-ttu-id="08e98-112">Каждый распределитель зависит от конкретного модуля и гарантирует, что текст функции будет иметь положительное смещение от базового модуля.</span><span class="sxs-lookup"><span data-stu-id="08e98-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="08e98-113">Память над базовым модулем может быть ценной, поэтому распределитель должен использоваться для выделения памяти только для тела функции.</span><span class="sxs-lookup"><span data-stu-id="08e98-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08e98-114">Требования</span><span class="sxs-lookup"><span data-stu-id="08e98-114">Requirements</span></span>  
 <span data-ttu-id="08e98-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08e98-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08e98-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="08e98-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="08e98-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08e98-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08e98-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08e98-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08e98-119">См. также</span><span class="sxs-lookup"><span data-stu-id="08e98-119">See also</span></span>

- [<span data-ttu-id="08e98-120">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="08e98-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
