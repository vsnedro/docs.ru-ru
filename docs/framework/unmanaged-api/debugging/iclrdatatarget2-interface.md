---
title: Интерфейс ICLRDataTarget2
ms.date: 03/30/2017
api_name:
- ICLRDataTarget2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataTarget2
helpviewer_keywords:
- ICLRDataTarget2 interface [.NET Framework debugging]
ms.assetid: 94249397-861b-4294-a538-cf01466a66d3
topic_type:
- apiref
ms.openlocfilehash: 6b2700b2f12e312f06640a06e5ec82fbc58f2ca9
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860461"
---
# <a name="iclrdatatarget2-interface"></a><span data-ttu-id="87379-102">Интерфейс ICLRDataTarget2</span><span class="sxs-lookup"><span data-stu-id="87379-102">ICLRDataTarget2 Interface</span></span>
<span data-ttu-id="87379-103">Подкласс [ICLRDataTarget](iclrdatatarget-interface.md) , используемый уровнем служб доступа к данным для управления областями виртуальной памяти в целевом процессе.</span><span class="sxs-lookup"><span data-stu-id="87379-103">A subclass of [ICLRDataTarget](iclrdatatarget-interface.md) that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87379-104">Методы</span><span class="sxs-lookup"><span data-stu-id="87379-104">Methods</span></span>  
  
|<span data-ttu-id="87379-105">Метод</span><span class="sxs-lookup"><span data-stu-id="87379-105">Method</span></span>|<span data-ttu-id="87379-106">Описание</span><span class="sxs-lookup"><span data-stu-id="87379-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87379-107">Метод AllocVirtual</span><span class="sxs-lookup"><span data-stu-id="87379-107">AllocVirtual Method</span></span>](iclrdatatarget2-allocvirtual-method.md)|<span data-ttu-id="87379-108">Выделяет память в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="87379-108">Allocates memory in the address space of the target process.</span></span>|  
|[<span data-ttu-id="87379-109">Метод FreeVirtual</span><span class="sxs-lookup"><span data-stu-id="87379-109">FreeVirtual Method</span></span>](iclrdatatarget2-freevirtual-method.md)|<span data-ttu-id="87379-110">Освобождает память, которая была ранее выделена в адресном пространстве целевого процесса.</span><span class="sxs-lookup"><span data-stu-id="87379-110">Frees memory that was previously allocated in the address space of the target process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87379-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="87379-111">Remarks</span></span>  
 <span data-ttu-id="87379-112">Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="87379-112">The API client (that is, the debugger) must implement this interface as appropriate for the particular target process.</span></span> <span data-ttu-id="87379-113">Например, реализация активного процесса будет отличаться от реализации дампа памяти.</span><span class="sxs-lookup"><span data-stu-id="87379-113">For example, a live process would have an implementation different from that of a memory dump.</span></span> <span data-ttu-id="87379-114">Целевой объект может не поддерживать изменение областей его памяти.</span><span class="sxs-lookup"><span data-stu-id="87379-114">The target may not support modification of its memory regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87379-115">Требования</span><span class="sxs-lookup"><span data-stu-id="87379-115">Requirements</span></span>  
 <span data-ttu-id="87379-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="87379-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87379-117">**Заголовок:** Клрдата. idl, Клрдата. h</span><span class="sxs-lookup"><span data-stu-id="87379-117">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="87379-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="87379-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="87379-119">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87379-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87379-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="87379-120">See also</span></span>

- [<span data-ttu-id="87379-121">Интерфейс ICLRDataTarget</span><span class="sxs-lookup"><span data-stu-id="87379-121">ICLRDataTarget Interface</span></span>](iclrdatatarget-interface.md)
- [<span data-ttu-id="87379-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="87379-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
