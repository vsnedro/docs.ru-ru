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
ms.openlocfilehash: a0d6f3e109f92ad44eeeb1b1dec05e53015992a6
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378364"
---
# <a name="icordebugthread4-interface"></a><span data-ttu-id="b8a00-102">Интерфейс ICorDebugThread4</span><span class="sxs-lookup"><span data-stu-id="b8a00-102">ICorDebugThread4 Interface</span></span>
<span data-ttu-id="b8a00-103">Предоставляет сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="b8a00-103">Provides thread blocking information.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b8a00-104">Методы</span><span class="sxs-lookup"><span data-stu-id="b8a00-104">Methods</span></span>  
  
|<span data-ttu-id="b8a00-105">Метод</span><span class="sxs-lookup"><span data-stu-id="b8a00-105">Method</span></span>|<span data-ttu-id="b8a00-106">Описание</span><span class="sxs-lookup"><span data-stu-id="b8a00-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b8a00-107">Метод GetBlockingObjects</span><span class="sxs-lookup"><span data-stu-id="b8a00-107">GetBlockingObjects Method</span></span>](icordebugthread4-getblockingobjects-method.md)|<span data-ttu-id="b8a00-108">Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.</span><span class="sxs-lookup"><span data-stu-id="b8a00-108">Provides an ordered enumeration of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures that provide thread blocking information.</span></span>|  
|[<span data-ttu-id="b8a00-109">Метод HadUnhandledException</span><span class="sxs-lookup"><span data-stu-id="b8a00-109">HadUnhandledException Method</span></span>](icordebugthread4-hadunhandledexception-method.md)|<span data-ttu-id="b8a00-110">Указывает, имел ли когда-либо поток необработанное исключение.</span><span class="sxs-lookup"><span data-stu-id="b8a00-110">Indicates whether the thread has ever had an unhandled exception.</span></span>|  
|[<span data-ttu-id="b8a00-111">Метод GetCurrentCustomDebuggerNotification</span><span class="sxs-lookup"><span data-stu-id="b8a00-111">GetCurrentCustomDebuggerNotification Method</span></span>](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|<span data-ttu-id="b8a00-112">Возвращает текущий объект [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) в текущем потоке.</span><span class="sxs-lookup"><span data-stu-id="b8a00-112">Gets the current [ICorDebugManagedCallback3::CustomNotification](icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b8a00-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="b8a00-113">Remarks</span></span>  
 <span data-ttu-id="b8a00-114">Этот интерфейс является логическим расширением интерфейсов ICorDebugThread, ICorDebugThread2 и [ICorDebugThread3](icordebugthread3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="b8a00-114">This interface is a logical extension of the ICorDebugThread, ICorDebugThread2, and [ICorDebugThread3](icordebugthread3-interface.md) interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b8a00-115">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="b8a00-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8a00-116">Требования</span><span class="sxs-lookup"><span data-stu-id="b8a00-116">Requirements</span></span>  
 <span data-ttu-id="b8a00-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8a00-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8a00-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b8a00-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b8a00-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8a00-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8a00-120">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8a00-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8a00-121">См. также</span><span class="sxs-lookup"><span data-stu-id="b8a00-121">See also</span></span>

- [<span data-ttu-id="b8a00-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b8a00-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="b8a00-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="b8a00-123">Debugging</span></span>](index.md)
