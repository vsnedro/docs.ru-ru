---
title: ICorDebugDebugEvent::Метод GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: ca6aba7897d9e97743d29db49bd058e140f84e6e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713591"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="c96d0-102">ICorDebugDebugEvent::Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="c96d0-102">ICorDebugDebugEvent::GetThread Method</span></span>

<span data-ttu-id="c96d0-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="c96d0-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c96d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c96d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c96d0-105">Parameters</span></span>  

 <span data-ttu-id="c96d0-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="c96d0-106">ppThread</span></span>  
 <span data-ttu-id="c96d0-107">[выходной] Указатель на адрес объекта ICorDebugThread, представляющего поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="c96d0-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c96d0-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c96d0-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c96d0-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c96d0-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c96d0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c96d0-110">Requirements</span></span>  

 <span data-ttu-id="c96d0-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c96d0-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c96d0-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c96d0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c96d0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c96d0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c96d0-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c96d0-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96d0-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c96d0-115">See also</span></span>

- [<span data-ttu-id="c96d0-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c96d0-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="c96d0-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c96d0-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
