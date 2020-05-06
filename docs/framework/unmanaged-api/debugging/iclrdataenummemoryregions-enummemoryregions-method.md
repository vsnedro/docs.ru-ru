---
title: Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegions.EnumMemoryRegions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions
helpviewer_keywords:
- ICLRDataEnumMemoryRegions::EnumMemoryRegions method [.NET Framework debugging]
- EnumMemoryRegions method [.NET Framework debugging]
ms.assetid: 22d2e339-f174-40b5-a478-0b744501566f
topic_type:
- apiref
ms.openlocfilehash: e6cdc924df126e56d2e7c8c9cb8762ee88712fcc
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860700"
---
# <a name="iclrdataenummemoryregionsenummemoryregions-method"></a><span data-ttu-id="1ba45-102">Метод ICLRDataEnumMemoryRegions::EnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="1ba45-102">ICLRDataEnumMemoryRegions::EnumMemoryRegions Method</span></span>
<span data-ttu-id="1ba45-103">Перечисляет указанные области памяти.</span><span class="sxs-lookup"><span data-stu-id="1ba45-103">Enumerates specified areas of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ba45-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1ba45-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMemoryRegions (  
    [in] ICLRDataEnumMemoryRegionsCallback  *callback,  
    [in] ULONG32                            miniDumpFlags,  
    [in] CLRDataEnumMemoryFlags             clrFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ba45-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1ba45-105">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="1ba45-106">окне Указатель на экземпляр [иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md) , вызываемый этим методом для каждой области памяти, перечисленной для уведомления отладчика о результатах.</span><span class="sxs-lookup"><span data-stu-id="1ba45-106">[in] A pointer to an [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance that is called by this method for each memory region being enumerated to notify the debugger of the result.</span></span>  
  
 <span data-ttu-id="1ba45-107">Перечисление областей памяти продолжится, даже если обратный вызов указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="1ba45-107">The enumeration of memory regions continues even if the callback indicates a failure.</span></span>  
  
 `miniDumpFlags`  
 <span data-ttu-id="1ba45-108">[in] Не используется.</span><span class="sxs-lookup"><span data-stu-id="1ba45-108">[in] Not used.</span></span>  
  
 `clrFlags`  
 <span data-ttu-id="1ba45-109">окне Значение перечисления [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) , указывающее области памяти для перечисления.</span><span class="sxs-lookup"><span data-stu-id="1ba45-109">[in] A value of the [CLRDataEnumMemoryFlags](clrdataenummemoryflags-enumeration.md) enumeration that specifies the regions of memory to be enumerated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ba45-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="1ba45-110">Remarks</span></span>  
 <span data-ttu-id="1ba45-111">Этот метод использует указанный экземпляр [иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md) для уведомления вызывающего объекта о результатах.</span><span class="sxs-lookup"><span data-stu-id="1ba45-111">This method uses the specified [ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md) instance to notify the caller of results.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ba45-112">Требования</span><span class="sxs-lookup"><span data-stu-id="1ba45-112">Requirements</span></span>  
 <span data-ttu-id="1ba45-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ba45-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ba45-114">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="1ba45-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1ba45-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ba45-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ba45-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ba45-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ba45-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="1ba45-117">See also</span></span>

- [<span data-ttu-id="1ba45-118">Интерфейс ICLRDataEnumMemoryRegions</span><span class="sxs-lookup"><span data-stu-id="1ba45-118">ICLRDataEnumMemoryRegions Interface</span></span>](iclrdataenummemoryregions-interface.md)
