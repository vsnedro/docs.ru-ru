---
title: Интерфейс ICorDebugMetaDataLocator
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
ms.openlocfilehash: dbf5c751e84dfd9bf0549e8ce79d07a90fb4a3b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710393"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="a685c-102">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="a685c-102">ICorDebugMetaDataLocator Interface</span></span>

<span data-ttu-id="a685c-103">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="a685c-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a685c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a685c-104">Methods</span></span>  
  
|<span data-ttu-id="a685c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a685c-105">Method</span></span>|<span data-ttu-id="a685c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a685c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a685c-107">Метод GetMetaData</span><span class="sxs-lookup"><span data-stu-id="a685c-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="a685c-108">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="a685c-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a685c-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a685c-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a685c-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a685c-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a685c-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a685c-111">Requirements</span></span>  

 <span data-ttu-id="a685c-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a685c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a685c-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a685c-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a685c-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a685c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a685c-115">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a685c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a685c-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a685c-116">See also</span></span>

- [<span data-ttu-id="a685c-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a685c-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a685c-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="a685c-118">Debugging</span></span>](index.md)
