---
title: Интерфейс ICorDebugDataTarget3
ms.date: 03/30/2017
ms.assetid: f477af85-994f-4df0-ae78-404ed252bf49
ms.openlocfilehash: e219c703ce2d8bb42f824a8892991f6803e6ef9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713734"
---
# <a name="icordebugdatatarget3-interface"></a><span data-ttu-id="84b72-102">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="84b72-102">ICorDebugDataTarget3 Interface</span></span>

<span data-ttu-id="84b72-103">Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) , чтобы предоставить сведения о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="84b72-103">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span>  
  
## <a name="method"></a><span data-ttu-id="84b72-104">Метод</span><span class="sxs-lookup"><span data-stu-id="84b72-104">Method</span></span>  
  
|<span data-ttu-id="84b72-105">Метод</span><span class="sxs-lookup"><span data-stu-id="84b72-105">Method</span></span>|<span data-ttu-id="84b72-106">Описание</span><span class="sxs-lookup"><span data-stu-id="84b72-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="84b72-107">Метод GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="84b72-107">GetLoadedModules Method</span></span>](icordebugdatatarget3-getloadedmodules-method.md)|<span data-ttu-id="84b72-108">Возвращает список модулей, загруженных на данный момент.</span><span class="sxs-lookup"><span data-stu-id="84b72-108">Gets a list of the modules that have been loaded so far.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84b72-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="84b72-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="84b72-110">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="84b72-110">This interface is available with .NET Native only.</span></span> <span data-ttu-id="84b72-111">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="84b72-111">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84b72-112">Требования</span><span class="sxs-lookup"><span data-stu-id="84b72-112">Requirements</span></span>  

 <span data-ttu-id="84b72-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84b72-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84b72-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84b72-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84b72-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84b72-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84b72-116">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84b72-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b72-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84b72-117">See also</span></span>

- [<span data-ttu-id="84b72-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="84b72-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="84b72-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="84b72-119">Debugging</span></span>](index.md)
