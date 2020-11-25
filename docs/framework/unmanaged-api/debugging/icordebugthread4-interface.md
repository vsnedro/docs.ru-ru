---
title: Интерфейс ICorDebugThread4
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
ms.openlocfilehash: 5c108420772be9e6d0932f3759f18da9446f99d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727943"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="d51d2-102">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="d51d2-102">ICorDebugThread4 Interface</span></span>

<span data-ttu-id="d51d2-103">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="d51d2-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d51d2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d51d2-104">Methods</span></span>  
  
|<span data-ttu-id="d51d2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d51d2-105">Method</span></span>|<span data-ttu-id="d51d2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d51d2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d51d2-107">Метод GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="d51d2-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="d51d2-108">Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="d51d2-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="d51d2-109">Метод HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="d51d2-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="d51d2-110">Указывает, имел ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="d51d2-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="d51d2-111">Метод GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="d51d2-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="d51d2-112">Возвращает текущий объект [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="d51d2-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d51d2-113">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d51d2-113">Remarks</span></span>  

 <span data-ttu-id="d51d2-114">Этот интерфейс является логическим расширением интерфейсов ICorDebugThread, ICorDebugThread2 и [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d51d2-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d51d2-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="d51d2-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d51d2-116">Требования</span><span class="sxs-lookup"><span data-stu-id="d51d2-116">Requirements</span></span>  

 <span data-ttu-id="d51d2-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d51d2-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d51d2-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d51d2-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d51d2-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d51d2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d51d2-120">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d51d2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d51d2-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d51d2-121">See also</span></span>

- [<span data-ttu-id="d51d2-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d51d2-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d51d2-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="d51d2-123">Debugging</span></span>](index.md)
