---
title: Интерфейс ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: 4acafafa284549fe1b078542a88c0818dcde3038
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686063"
---
# <a name="icorprofilerinfo7-interface"></a><span data-ttu-id="cefe2-102">Интерфейс ICorProfilerInfo7</span><span class="sxs-lookup"><span data-stu-id="cefe2-102">ICorProfilerInfo7 Interface</span></span>

<span data-ttu-id="cefe2-103">[Поддерживается в .NET Framework 4.6.1 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="cefe2-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="cefe2-104">Подкласс [ICorProfilerInfo6](icorprofilerinfo6-interface.md) , предоставляющий метод для применения вновь заданных метаданных к модулю и предоставляющий доступ к потоку символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="cefe2-104">A subclass of [ICorProfilerInfo6](icorprofilerinfo6-interface.md) that provides a method to apply newly defined metadata to a module and that provides access to an in-memory symbol stream.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cefe2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="cefe2-105">Methods</span></span>  
  
|<span data-ttu-id="cefe2-106">Метод</span><span class="sxs-lookup"><span data-stu-id="cefe2-106">Method</span></span>|<span data-ttu-id="cefe2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="cefe2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cefe2-108">Метод ApplyMetaData</span><span class="sxs-lookup"><span data-stu-id="cefe2-108">ApplyMetaData Method</span></span>](icorprofilerinfo7-applymetadata-method.md)|<span data-ttu-id="cefe2-109">Применяет метаданные, которые были недавно определены `IMetadataEmit::Define*` методами, к указанному модулю.</span><span class="sxs-lookup"><span data-stu-id="cefe2-109">Applies the metadata newly defined by the `IMetadataEmit::Define*` methods to a specified module.</span></span>|  
|[<span data-ttu-id="cefe2-110">Метод GetInMemorySymbolsLength</span><span class="sxs-lookup"><span data-stu-id="cefe2-110">GetInMemorySymbolsLength Method</span></span>](icorprofilerinfo7-getinmemorysymbolslength-method.md)|<span data-ttu-id="cefe2-111">Возвращает длину потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="cefe2-111">Returns the length of an in-memory symbol stream.</span></span>|  
|[<span data-ttu-id="cefe2-112">ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="cefe2-112">ReadInMemorySymbols</span></span>](icorprofilerinfo7-readinmemorysymbols.md)|<span data-ttu-id="cefe2-113">Считывает байты из потока символов в памяти.</span><span class="sxs-lookup"><span data-stu-id="cefe2-113">Reads bytes from an in-memory symbol stream.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cefe2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="cefe2-114">Requirements</span></span>  

 <span data-ttu-id="cefe2-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cefe2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cefe2-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cefe2-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cefe2-117">**.NET Framework версии:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cefe2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cefe2-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="cefe2-118">See also</span></span>

- [<span data-ttu-id="cefe2-119">Профилирующие интерфейсы</span><span class="sxs-lookup"><span data-stu-id="cefe2-119">Profiling Interfaces</span></span>](profiling-interfaces.md)
