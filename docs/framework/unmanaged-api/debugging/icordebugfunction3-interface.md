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
ms.openlocfilehash: 71aa482cc2268da17f1376d8c305dd6a818d92d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213170"
---
# <a name="icordebugfunction3-interface"></a><span data-ttu-id="3d8ff-102">Интерфейс ICorDebugFunction3</span><span class="sxs-lookup"><span data-stu-id="3d8ff-102">ICorDebugFunction3 Interface</span></span>
<span data-ttu-id="3d8ff-103">[Поддерживается в .NET Framework 4.5.2 и более поздних версиях.]</span><span class="sxs-lookup"><span data-stu-id="3d8ff-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="3d8ff-104">Логически расширяет интерфейс ICorDebugFunction для предоставления доступа к коду из запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="3d8ff-104">Logically extends the ICorDebugFunction interface to provide access to code from a ReJIT request.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3d8ff-105">Методы</span><span class="sxs-lookup"><span data-stu-id="3d8ff-105">Methods</span></span>  
  
|<span data-ttu-id="3d8ff-106">Метод</span><span class="sxs-lookup"><span data-stu-id="3d8ff-106">Method</span></span>|<span data-ttu-id="3d8ff-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3d8ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3d8ff-108">Метод GetActiveReJitRequestILCode</span><span class="sxs-lookup"><span data-stu-id="3d8ff-108">GetActiveReJitRequestILCode Method</span></span>](icordebugfunction3-getactiverejitrequestilcode-method.md)|<span data-ttu-id="3d8ff-109">Возвращает указатель интерфейса на [икордебугилкоде](icordebugilcode-interface.md) , содержащий Il из активного запроса ReJIT.</span><span class="sxs-lookup"><span data-stu-id="3d8ff-109">Gets an interface pointer to an [ICorDebugILCode](icordebugilcode-interface.md) that contains the IL from an active ReJIT request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d8ff-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d8ff-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d8ff-111">Требования</span><span class="sxs-lookup"><span data-stu-id="3d8ff-111">Requirements</span></span>  
 <span data-ttu-id="3d8ff-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d8ff-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d8ff-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d8ff-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d8ff-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d8ff-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d8ff-115">**.NET Framework версии:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d8ff-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d8ff-116">См. также</span><span class="sxs-lookup"><span data-stu-id="3d8ff-116">See also</span></span>

- [<span data-ttu-id="3d8ff-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3d8ff-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3d8ff-118">Отладка</span><span class="sxs-lookup"><span data-stu-id="3d8ff-118">Debugging</span></span>](index.md)
- [<span data-ttu-id="3d8ff-119">ReJIT: руководство</span><span class="sxs-lookup"><span data-stu-id="3d8ff-119">ReJIT: A How-To Guide</span></span>](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
