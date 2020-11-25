---
title: Интерфейс ICorDebugFunction3
ms.date: 03/30/2017
api_name:
- ICorDebugFunction3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b22717b9-ead5-4eea-887e-789b52d613dc
topic_type:
- apiref
ms.openlocfilehash: 17eda7470e5f2e4b41d1f2ed164843eaeeedea93
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695874"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="745e2-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="745e2-102">ICorDebugFunction3 Interface</span></span>

<span data-ttu-id="745e2-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="745e2-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="745e2-104">Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="745e2-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="745e2-105">Методы</span><span class="sxs-lookup"><span data-stu-id="745e2-105">Methods</span></span>  
  
|<span data-ttu-id="745e2-106">Метод</span><span class="sxs-lookup"><span data-stu-id="745e2-106">Method</span></span>|<span data-ttu-id="745e2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="745e2-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="745e2-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="745e2-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="745e2-109">Возвращает указатель интерфейса на [икордебугилкоде](icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="745e2-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="745e2-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="745e2-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="745e2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="745e2-111">Requirements</span></span>  

 <span data-ttu-id="745e2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="745e2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="745e2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="745e2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="745e2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="745e2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="745e2-115">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="745e2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="745e2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="745e2-116">See also</span></span>

- [<span data-ttu-id="745e2-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="745e2-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="745e2-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="745e2-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="745e2-119">ReJIT: руководство по How-To</span><span class="sxs-lookup"><span data-stu-id="745e2-119">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
