---
title: Интерфейс ICorDebugLoadedModule
ms.date: 03/30/2017
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
ms.openlocfilehash: d9b8245d8c37867971aa48ed3befb9cf22bd5b04
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210167"
---
# <a name="icordebugloadedmodule-interface"></a><span data-ttu-id="deecf-102">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="deecf-102">ICorDebugLoadedModule Interface</span></span>
<span data-ttu-id="deecf-103">Предоставляет сведения о загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="deecf-103">Provides information about a loaded module.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="deecf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="deecf-104">Methods</span></span>  
  
|<span data-ttu-id="deecf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="deecf-105">Method</span></span>|<span data-ttu-id="deecf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="deecf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="deecf-107">Метод GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="deecf-107">GetBaseAddress Method</span></span>](icordebugloadedmodule-getbaseaddress-method.md)|<span data-ttu-id="deecf-108">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="deecf-108">Gets the base address of the loaded module.</span></span>|  
|[<span data-ttu-id="deecf-109">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="deecf-109">GetName Method</span></span>](icordebugloadedmodule-getname-method.md)|<span data-ttu-id="deecf-110">Получает имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="deecf-110">Gets the name of the loaded module.</span></span>|  
|[<span data-ttu-id="deecf-111">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="deecf-111">GetSize Method</span></span>](icordebugloadedmodule-getsize-method.md)|<span data-ttu-id="deecf-112">Возвращает размер в байтах загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="deecf-112">Gets the size in bytes of the loaded module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="deecf-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="deecf-113">Remarks</span></span>  
 <span data-ttu-id="deecf-114">Интерфейс `ICorDebugLoadedModule` реализуется с помощью отладчика и используется интерфейсами отладки среды CLR для получения сведений о загруженном модуле из отладчика.</span><span class="sxs-lookup"><span data-stu-id="deecf-114">The `ICorDebugLoadedModule` interface is implemented by a debugger and is used by the CLR debugging interfaces to get information about the loaded module from the debugger.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="deecf-115">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="deecf-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="deecf-116">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="deecf-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="deecf-117">Требования</span><span class="sxs-lookup"><span data-stu-id="deecf-117">Requirements</span></span>  
 <span data-ttu-id="deecf-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="deecf-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="deecf-119">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="deecf-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="deecf-120">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="deecf-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="deecf-121">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="deecf-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="deecf-122">См. также</span><span class="sxs-lookup"><span data-stu-id="deecf-122">See also</span></span>

- [<span data-ttu-id="deecf-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="deecf-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="deecf-124">Отладка</span><span class="sxs-lookup"><span data-stu-id="deecf-124">Debugging</span></span>](index.md)
