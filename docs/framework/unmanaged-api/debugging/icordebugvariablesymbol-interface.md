---
title: Интерфейс ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 3d808fd49eb7767f1f48ad4e07d8ba7e47c8f34b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679485"
---
# <a name="icordebugvariablesymbol-interface"></a><span data-ttu-id="563b4-102">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="563b4-102">ICorDebugVariableSymbol Interface</span></span>

<span data-ttu-id="563b4-103">Извлекает сведения символа отладки для статического поля.</span><span class="sxs-lookup"><span data-stu-id="563b4-103">Retrieves the debug symbol information for a variable.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="563b4-104">Методы</span><span class="sxs-lookup"><span data-stu-id="563b4-104">Methods</span></span>  
  
|<span data-ttu-id="563b4-105">Метод</span><span class="sxs-lookup"><span data-stu-id="563b4-105">Method</span></span>|<span data-ttu-id="563b4-106">Описание</span><span class="sxs-lookup"><span data-stu-id="563b4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="563b4-107">Метод GetName</span><span class="sxs-lookup"><span data-stu-id="563b4-107">GetName Method</span></span>](icordebugvariablesymbol-getname-method.md)|<span data-ttu-id="563b4-108">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="563b4-108">Gets the name of a variable.</span></span>|  
|[<span data-ttu-id="563b4-109">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="563b4-109">GetSize Method</span></span>](icordebugvariablesymbol-getsize-method.md)|<span data-ttu-id="563b4-110">Получает размер переменной в байтах.</span><span class="sxs-lookup"><span data-stu-id="563b4-110">Gets the size of a variable in bytes.</span></span>|  
|[<span data-ttu-id="563b4-111">Метод GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="563b4-111">GetSlotIndex Method</span></span>](icordebugvariablesymbol-getslotindex-method.md)|<span data-ttu-id="563b4-112">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="563b4-112">Gets the managed slot index of a local variable.</span></span>|  
|[<span data-ttu-id="563b4-113">Метод GetValue</span><span class="sxs-lookup"><span data-stu-id="563b4-113">GetValue Method</span></span>](icordebugvariablesymbol-getvalue-method.md)|<span data-ttu-id="563b4-114">Возвращает значение переменной в виде массива байтов.</span><span class="sxs-lookup"><span data-stu-id="563b4-114">Gets the value of a variable as a byte array.</span></span>|  
|[<span data-ttu-id="563b4-115">Метод SetValue</span><span class="sxs-lookup"><span data-stu-id="563b4-115">SetValue Method</span></span>](icordebugvariablesymbol-setvalue-method.md)|<span data-ttu-id="563b4-116">Присваивает переменной значение массива байтов.</span><span class="sxs-lookup"><span data-stu-id="563b4-116">Assigns the value of a byte array to a variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="563b4-117">Комментарии</span><span class="sxs-lookup"><span data-stu-id="563b4-117">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="563b4-118">Этот интерфейс доступен только в .NET Native.</span><span class="sxs-lookup"><span data-stu-id="563b4-118">This interface is available with .NET Native only.</span></span> <span data-ttu-id="563b4-119">При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="563b4-119">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="563b4-120">Требования</span><span class="sxs-lookup"><span data-stu-id="563b4-120">Requirements</span></span>  

 <span data-ttu-id="563b4-121">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="563b4-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="563b4-122">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="563b4-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="563b4-123">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="563b4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="563b4-124">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="563b4-124">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="563b4-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="563b4-125">See also</span></span>

- [<span data-ttu-id="563b4-126">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="563b4-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="563b4-127">Отладка</span><span class="sxs-lookup"><span data-stu-id="563b4-127">Debugging</span></span>](index.md)
