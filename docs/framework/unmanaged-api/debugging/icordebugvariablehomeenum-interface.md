---
title: Интерфейс ICorDebugVariableHomeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: d5962de8cc2762f6ecf4864c5255da0fe83918e4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396532"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="caf0e-102">Интерфейс ICorDebugVariableHomeEnum</span><span class="sxs-lookup"><span data-stu-id="caf0e-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="caf0e-103">Предоставляет перечислитель для локальных переменных и аргументов в функции.</span><span class="sxs-lookup"><span data-stu-id="caf0e-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="caf0e-104">Методы</span><span class="sxs-lookup"><span data-stu-id="caf0e-104">Methods</span></span>  
  
|<span data-ttu-id="caf0e-105">Метод</span><span class="sxs-lookup"><span data-stu-id="caf0e-105">Method</span></span>|<span data-ttu-id="caf0e-106">Описание</span><span class="sxs-lookup"><span data-stu-id="caf0e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="caf0e-107">Метод Next</span><span class="sxs-lookup"><span data-stu-id="caf0e-107">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="caf0e-108">Возвращает указанное число экземпляров [ICorDebugVariableHome](icordebugvariablehome-interface.md) , содержащих сведения о локальных переменных и аргументах в функции.</span><span class="sxs-lookup"><span data-stu-id="caf0e-108">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caf0e-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="caf0e-109">Remarks</span></span>  
 <span data-ttu-id="caf0e-110">`ICorDebugVariableHomeEnum`Интерфейс реализует интерфейс ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="caf0e-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="caf0e-111">`ICorDebugVariableHomeEnum`Экземпляр заполняется экземплярами [ICorDebugVariableHome](icordebugvariablehome-interface.md) путем вызова метода [ICorDebugCode4:: енумератевариаблехомес](icordebugcode4-enumeratevariablehomes-method.md) .</span><span class="sxs-lookup"><span data-stu-id="caf0e-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="caf0e-112">Каждый экземпляр [ICorDebugVariableHome](icordebugvariablehome-interface.md) в коллекции представляет локальную переменную или аргумент в функции.</span><span class="sxs-lookup"><span data-stu-id="caf0e-112">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="caf0e-113">Объекты [ICorDebugVariableHome](icordebugvariablehome-interface.md) в коллекции можно перечислить, вызвав метод [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .</span><span class="sxs-lookup"><span data-stu-id="caf0e-113">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caf0e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="caf0e-114">Requirements</span></span>  
 <span data-ttu-id="caf0e-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caf0e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caf0e-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="caf0e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caf0e-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caf0e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caf0e-118">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caf0e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caf0e-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="caf0e-119">See also</span></span>

- [<span data-ttu-id="caf0e-120">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="caf0e-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="caf0e-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="caf0e-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
