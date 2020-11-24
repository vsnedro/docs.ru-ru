---
title: 'Метод ICorProfilerInfo7:: GetInMemorySymbolsLength'
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type:
- COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
ms.openlocfilehash: 46ffa5cb4fac6988240d32cb1939cc25bdf0a412
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686076"
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="c6074-102">Метод ICorProfilerInfo7:: GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="c6074-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>

<span data-ttu-id="c6074-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="c6074-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="c6074-104">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="c6074-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6074-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6074-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6074-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6074-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="c6074-107">окне Идентификатор модуля, содержащего поток в памяти.</span><span class="sxs-lookup"><span data-stu-id="c6074-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="c6074-108">пкаунтсимболбитес</span><span class="sxs-lookup"><span data-stu-id="c6074-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="c6074-109">заполняет Указатель на значение, `DWORD` которое при возврате метода содержит длину потока в байтах.</span><span class="sxs-lookup"><span data-stu-id="c6074-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6074-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c6074-110">Return Value</span></span>  

 <span data-ttu-id="c6074-111">Метод возвращает значение `S_OK` , если длина потока памяти может быть определена, даже если она равна нулю (0).</span><span class="sxs-lookup"><span data-stu-id="c6074-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="c6074-112">Метод возвращает значение, `CORPROF_E_MODULE_IS_DYNAMIC` Если метод был создан с помощью <xref:System.Reflection.Emit?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c6074-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c6074-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c6074-113">Remarks</span></span>  

 <span data-ttu-id="c6074-114">Если модуль содержит символы в памяти, длина потока помещается в `pCountSymbolBytes` .</span><span class="sxs-lookup"><span data-stu-id="c6074-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="c6074-115">Если у модуля нет символов в памяти, то `*pCountSymbolBytes = 0` .</span><span class="sxs-lookup"><span data-stu-id="c6074-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c6074-116">Текущая реализация не поддерживает отражение. Emit.</span><span class="sxs-lookup"><span data-stu-id="c6074-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="c6074-117">Если модуль был создан с помощью отражения. Emit, метод возвращает значение `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="c6074-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6074-118">Требования</span><span class="sxs-lookup"><span data-stu-id="c6074-118">Requirements</span></span>  

 <span data-ttu-id="c6074-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6074-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6074-120">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c6074-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c6074-121">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6074-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6074-122">**.NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6074-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6074-123">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c6074-123">See also</span></span>

- [<span data-ttu-id="c6074-124">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="c6074-124">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
