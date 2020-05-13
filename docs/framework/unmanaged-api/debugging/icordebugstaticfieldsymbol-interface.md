---
title: Интерфейс ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: f9b82f0f98a668555a8096d7575c049c31cae93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379441"
---
# <a name="icordebugstaticfieldsymbol-interface"></a><span data-ttu-id="80832-102">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="80832-102">ICorDebugStaticFieldSymbol Interface</span></span>
<span data-ttu-id="80832-103">Представляет сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="80832-103">Represents the debug symbol information for a static field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80832-104">Методы</span><span class="sxs-lookup"><span data-stu-id="80832-104">Methods</span></span>  
  
|<span data-ttu-id="80832-105">Метод</span><span class="sxs-lookup"><span data-stu-id="80832-105">Method</span></span>|<span data-ttu-id="80832-106">Описание</span><span class="sxs-lookup"><span data-stu-id="80832-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80832-107">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="80832-107">GetAddress Method</span></span>](icordebugstaticfieldsymbol-getaddress-method.md)|<span data-ttu-id="80832-108">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="80832-108">Gets the address of the static field.</span></span>|  
|[<span data-ttu-id="80832-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="80832-109">GetName Method</span></span>](icordebugstaticfieldsymbol-getname-method.md)|<span data-ttu-id="80832-110">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="80832-110">Gets the name of the static field.</span></span>|  
|[<span data-ttu-id="80832-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="80832-111">GetSize Method</span></span>](icordebugstaticfieldsymbol-getsize-method.md)|<span data-ttu-id="80832-112">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="80832-112">Gets the size in bytes of the static field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80832-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="80832-113">Remarks</span></span>  
 <span data-ttu-id="80832-114">Интерфейс `ICorDebugStaticFieldSymbol` используется для извлечения сведений отладочного символа для статического поля.</span><span class="sxs-lookup"><span data-stu-id="80832-114">The `ICorDebugStaticFieldSymbol` interface is used to retrieve the debug symbol information for a static field.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="80832-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="80832-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="80832-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="80832-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80832-117">Требования</span><span class="sxs-lookup"><span data-stu-id="80832-117">Requirements</span></span>  
 <span data-ttu-id="80832-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80832-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80832-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80832-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80832-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80832-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80832-121">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80832-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80832-122">См. также</span><span class="sxs-lookup"><span data-stu-id="80832-122">See also</span></span>

- [<span data-ttu-id="80832-123">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="80832-123">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="80832-124">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="80832-124">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="80832-125">Отладка</span><span class="sxs-lookup"><span data-stu-id="80832-125">Debugging</span></span>](index.md)
