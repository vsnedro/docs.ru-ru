---
title: Интерфейс ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: e6712dca776bf4c20ce7fc8568e94399a81beecb
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379289"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="383b2-102">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="383b2-102">ICorDebugSymbolProvider2 Interface</span></span>
<span data-ttu-id="383b2-103">Логически расширяет интерфейс [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) для получения дополнительных сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="383b2-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="383b2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="383b2-104">Methods</span></span>  
  
|<span data-ttu-id="383b2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="383b2-105">Method</span></span>|<span data-ttu-id="383b2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="383b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="383b2-107">Метод GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="383b2-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="383b2-108">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="383b2-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="383b2-109">Метод GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="383b2-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="383b2-110">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="383b2-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="383b2-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="383b2-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="383b2-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="383b2-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="383b2-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="383b2-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="383b2-114">Требования</span><span class="sxs-lookup"><span data-stu-id="383b2-114">Requirements</span></span>  
 <span data-ttu-id="383b2-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="383b2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="383b2-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="383b2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="383b2-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="383b2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="383b2-118">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="383b2-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="383b2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="383b2-119">See also</span></span>

- [<span data-ttu-id="383b2-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="383b2-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="383b2-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="383b2-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="383b2-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="383b2-122">Debugging</span></span>](index.md)
