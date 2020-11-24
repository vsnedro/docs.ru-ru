---
title: Интерфейс ICorDebugSymbolProvider2
ms.date: 03/30/2017
ms.assetid: 1c9c3d92-f0de-4d4d-87f1-0c702a4808af
ms.openlocfilehash: 3bef03e9e85224058bc17e1f0ce8746e98aa30f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688345"
---
# <a name="icordebugsymbolprovider2-interface"></a><span data-ttu-id="73a68-102">Интерфейс ICorDebugSymbolProvider2</span><span class="sxs-lookup"><span data-stu-id="73a68-102">ICorDebugSymbolProvider2 Interface</span></span>

<span data-ttu-id="73a68-103">Логически расширяет интерфейс [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) для получения дополнительных сведений об отладочных символах.</span><span class="sxs-lookup"><span data-stu-id="73a68-103">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73a68-104">Методы</span><span class="sxs-lookup"><span data-stu-id="73a68-104">Methods</span></span>  
  
|<span data-ttu-id="73a68-105">Метод</span><span class="sxs-lookup"><span data-stu-id="73a68-105">Method</span></span>|<span data-ttu-id="73a68-106">Описание</span><span class="sxs-lookup"><span data-stu-id="73a68-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73a68-107">Метод GetFrameProps</span><span class="sxs-lookup"><span data-stu-id="73a68-107">GetFrameProps Method</span></span>](icordebugsymbolprovider2-getframeprops-method.md)|<span data-ttu-id="73a68-108">Возвращает начальный относительный виртуальный адрес метода и родительского фрейма для указанного относительного виртуального адреса кода.</span><span class="sxs-lookup"><span data-stu-id="73a68-108">Returns the method starting relative virtual address of a method and the parent frame given a code relative virtual address.</span></span>|  
|[<span data-ttu-id="73a68-109">Метод GetGenericDictionaryInfo</span><span class="sxs-lookup"><span data-stu-id="73a68-109">GetGenericDictionaryInfo Method</span></span>](icordebugsymbolprovider2-getgenericdictionaryinfo-method.md)|<span data-ttu-id="73a68-110">Получает универсальную карту словаря</span><span class="sxs-lookup"><span data-stu-id="73a68-110">Retrieves a generic dictionary map.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73a68-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="73a68-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="73a68-112">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="73a68-112">This interface is available with .NET Native only.</span></span> <span data-ttu-id="73a68-113">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="73a68-113">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73a68-114">Требования</span><span class="sxs-lookup"><span data-stu-id="73a68-114">Requirements</span></span>  

 <span data-ttu-id="73a68-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73a68-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73a68-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="73a68-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="73a68-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="73a68-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="73a68-118">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73a68-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73a68-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="73a68-119">See also</span></span>

- [<span data-ttu-id="73a68-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="73a68-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="73a68-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="73a68-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="73a68-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="73a68-122">Debugging</span></span>](index.md)
