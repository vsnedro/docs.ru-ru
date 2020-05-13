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
ms.openlocfilehash: 7b7b7a42edea775d1aaa850ccfc532ef86749991
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210029"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="ad5b2-102">Интерфейс ICorDebugMetaDataLocator</span><span class="sxs-lookup"><span data-stu-id="ad5b2-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="ad5b2-103">Предоставляет сведения о метаданных для отладчика.</span><span class="sxs-lookup"><span data-stu-id="ad5b2-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ad5b2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ad5b2-104">Methods</span></span>  
  
|<span data-ttu-id="ad5b2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ad5b2-105">Method</span></span>|<span data-ttu-id="ad5b2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ad5b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad5b2-107">Метод GetMetaData</span><span class="sxs-lookup"><span data-stu-id="ad5b2-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="ad5b2-108">Запрашивает у отладчика возврат полного пути к модулю, метаданные которого необходимы для завершения запрошенной отладчиком операции.</span><span class="sxs-lookup"><span data-stu-id="ad5b2-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad5b2-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="ad5b2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ad5b2-110">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="ad5b2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad5b2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="ad5b2-111">Requirements</span></span>  
 <span data-ttu-id="ad5b2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad5b2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad5b2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ad5b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ad5b2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad5b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ad5b2-115">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad5b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5b2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="ad5b2-116">See also</span></span>

- [<span data-ttu-id="ad5b2-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="ad5b2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="ad5b2-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="ad5b2-118">Debugging</span></span>](index.md)
