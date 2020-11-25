---
title: Метод IMethodMalloc::Alloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
ms.openlocfilehash: 58809f12e4dd4419b754caafc3f8b883b8bc5089
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721170"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="48e42-102">Метод IMethodMalloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="48e42-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="48e42-103">Пытается выделить указанный объем памяти для нового текста функции MSIL.</span><span class="sxs-lookup"><span data-stu-id="48e42-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="48e42-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48e42-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="48e42-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="48e42-105">Parameters</span></span>

`cb`\
<span data-ttu-id="48e42-106">окне Число байтов, которое необходимо выделить для тела метода.</span><span class="sxs-lookup"><span data-stu-id="48e42-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="48e42-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="48e42-107">Remarks</span></span>

 <span data-ttu-id="48e42-108">Выделенная память будет начинаться с адреса, превышающего базовый адрес модуля, связанного с этим распределителем.</span><span class="sxs-lookup"><span data-stu-id="48e42-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="48e42-109">Иными словами, каждый распределитель создается для конкретного модуля и пытается выделить память с положительным смещением от его базового адреса.</span><span class="sxs-lookup"><span data-stu-id="48e42-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="48e42-110">Если `Alloc` не удается выделить запрошенное число байтов по адресу, превышающему базовый адрес модуля, он возвращает E_OUTOFMEMORY, независимо от фактического объема доступной памяти.</span><span class="sxs-lookup"><span data-stu-id="48e42-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="48e42-111">`Alloc`Метод следует использовать в сочетании с методом [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) .</span><span class="sxs-lookup"><span data-stu-id="48e42-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="48e42-112">Требования</span><span class="sxs-lookup"><span data-stu-id="48e42-112">Requirements</span></span>

 <span data-ttu-id="48e42-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48e42-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="48e42-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="48e42-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="48e42-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48e42-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="48e42-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48e42-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="48e42-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="48e42-117">See also</span></span>

- [<span data-ttu-id="48e42-118">Интерфейс IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="48e42-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
