---
title: Интерфейс ICorDebugProcess3
ms.date: 03/30/2017
api_name:
- ICorDebugProcess3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess3
helpviewer_keywords:
- ICorDebugProcess3 interface [.NET Framework debugging]
ms.assetid: ced9c82e-d7b0-4806-a151-98b6611d3097
topic_type:
- apiref
ms.openlocfilehash: ef8dbd5253c02355f85fba626fa7e68ed62df4bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686461"
---
# <a name="icordebugprocess3-interface"></a><span data-ttu-id="451bf-102">Интерфейс ICorDebugProcess3</span><span class="sxs-lookup"><span data-stu-id="451bf-102">ICorDebugProcess3 Interface</span></span>

<span data-ttu-id="451bf-103">Управляет пользовательскими уведомлениями отладчика.</span><span class="sxs-lookup"><span data-stu-id="451bf-103">Controls custom debugger notifications.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="451bf-104">Методы</span><span class="sxs-lookup"><span data-stu-id="451bf-104">Methods</span></span>  
  
|<span data-ttu-id="451bf-105">Метод</span><span class="sxs-lookup"><span data-stu-id="451bf-105">Method</span></span>|<span data-ttu-id="451bf-106">Описание</span><span class="sxs-lookup"><span data-stu-id="451bf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="451bf-107">Метод SetEnableCustomNotification</span><span class="sxs-lookup"><span data-stu-id="451bf-107">SetEnableCustomNotification Method</span></span>](icordebugprocess3-setenablecustomnotification-method.md)|<span data-ttu-id="451bf-108">Включает и отключает настраиваемые уведомления отладчика указанного типа.</span><span class="sxs-lookup"><span data-stu-id="451bf-108">Enables and disables custom debugger notifications of the specified type.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="451bf-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="451bf-109">Remarks</span></span>  

 <span data-ttu-id="451bf-110">Этот интерфейс логически расширяет интерфейсы ICorDebugProcess и ICorDebugProcess2.</span><span class="sxs-lookup"><span data-stu-id="451bf-110">This interface logically extends the ICorDebugProcess and ICorDebugProcess2 interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="451bf-111">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="451bf-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="451bf-112">Требования</span><span class="sxs-lookup"><span data-stu-id="451bf-112">Requirements</span></span>  

 <span data-ttu-id="451bf-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="451bf-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="451bf-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="451bf-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="451bf-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="451bf-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="451bf-116">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="451bf-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="451bf-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="451bf-117">See also</span></span>

- [<span data-ttu-id="451bf-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="451bf-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="451bf-119">Отладка</span><span class="sxs-lookup"><span data-stu-id="451bf-119">Debugging</span></span>](index.md)
