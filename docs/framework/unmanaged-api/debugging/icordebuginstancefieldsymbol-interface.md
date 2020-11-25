---
title: Интерфейс ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 4ef0f7a46acf7e9df732d630c9eb22044e09d658
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724901"
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="0b406-102">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0b406-102">ICorDebugInstanceFieldSymbol Interface</span></span>

<span data-ttu-id="0b406-103">Представляет сведения отладочного символа для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0b406-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0b406-104">Методы</span><span class="sxs-lookup"><span data-stu-id="0b406-104">Methods</span></span>  
  
|<span data-ttu-id="0b406-105">Метод</span><span class="sxs-lookup"><span data-stu-id="0b406-105">Method</span></span>|<span data-ttu-id="0b406-106">Описание</span><span class="sxs-lookup"><span data-stu-id="0b406-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0b406-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="0b406-107">GetName Method</span></span>](icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="0b406-108">Получает имя поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0b406-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="0b406-109">Метод GetOffset</span><span class="sxs-lookup"><span data-stu-id="0b406-109">GetOffset Method</span></span>](icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="0b406-110">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="0b406-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="0b406-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="0b406-111">GetSize Method</span></span>](icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="0b406-112">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="0b406-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b406-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0b406-113">Remarks</span></span>  

 <span data-ttu-id="0b406-114">Интерфейс `ICorDebugInstanceFieldSymbol` используется для получения сведений символа отладки для поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="0b406-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b406-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="0b406-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="0b406-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="0b406-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b406-117">Требования</span><span class="sxs-lookup"><span data-stu-id="0b406-117">Requirements</span></span>  

 <span data-ttu-id="0b406-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b406-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b406-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b406-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b406-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b406-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b406-121">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b406-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b406-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0b406-122">See also</span></span>

- [<span data-ttu-id="0b406-123">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0b406-123">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="0b406-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0b406-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="0b406-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="0b406-125">Debugging</span></span>](index.md)
