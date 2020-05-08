---
title: Интерфейс ICorDebugComObjectValue Interface
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: 528db447df4d71d67441b05ad29e6a900c59afbb
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892824"
---
# <a name="icordebugcomobjectvalue-interface"></a><span data-ttu-id="c4442-102">Интерфейс ICorDebugComObjectValue Interface</span><span class="sxs-lookup"><span data-stu-id="c4442-102">ICorDebugComObjectValue Interface</span></span>
<span data-ttu-id="c4442-103">Предоставляет методы для получения сведений, связанных с вызываемой оболочкой времени выполнения (RCW).</span><span class="sxs-lookup"><span data-stu-id="c4442-103">Provides methods to retrieve information associated with a runtime callable wrapper (RCW).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c4442-104">Методы</span><span class="sxs-lookup"><span data-stu-id="c4442-104">Methods</span></span>  
  
|<span data-ttu-id="c4442-105">Метод</span><span class="sxs-lookup"><span data-stu-id="c4442-105">Method</span></span>|<span data-ttu-id="c4442-106">Описание</span><span class="sxs-lookup"><span data-stu-id="c4442-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c4442-107">Метод GetCachedInterfacePointers</span><span class="sxs-lookup"><span data-stu-id="c4442-107">GetCachedInterfacePointers Method</span></span>](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|<span data-ttu-id="c4442-108">Возвращает необработанные указатели интерфейса, кэшированные в текущей RCW.</span><span class="sxs-lookup"><span data-stu-id="c4442-108">Gets the raw interface pointers cached on the current RCW.</span></span>|  
|[<span data-ttu-id="c4442-109">Метод GetCachedInterfaceTypes</span><span class="sxs-lookup"><span data-stu-id="c4442-109">GetCachedInterfaceTypes Method</span></span>](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|<span data-ttu-id="c4442-110">Предоставляет перечислитель для типов интерфейса, к которым был применен регистр текущего объекта или использован в качестве.</span><span class="sxs-lookup"><span data-stu-id="c4442-110">Provides an enumerator for the interface types that the current object has been cased to or used as.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4442-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4442-111">Remarks</span></span>  
 <span data-ttu-id="c4442-112">Чтобы проверить, представляет ли экземпляр интерфейса "ICorDebugValue" RCW, отладчик вызывает метод `QueryInterface` "ICorDebugValue" с. `IID_ICorDebugComObjectValue`</span><span class="sxs-lookup"><span data-stu-id="c4442-112">To check whether an instance of an "ICorDebugValue" interface represents an RCW, a debugger calls `QueryInterface` on "ICorDebugValue" with `IID_ICorDebugComObjectValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4442-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c4442-113">Requirements</span></span>  
 <span data-ttu-id="c4442-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4442-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4442-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4442-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4442-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4442-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4442-117">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4442-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4442-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4442-118">See also</span></span>

- [<span data-ttu-id="c4442-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c4442-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c4442-120">Отладка</span><span class="sxs-lookup"><span data-stu-id="c4442-120">Debugging</span></span>](index.md)
