---
title: ICorDebugDebugEvent::Метод GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: acce18517c105739417fc734b49ff004ca9546dc
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976386"
---
# <a name="icordebugdebugeventgetthread-method"></a><span data-ttu-id="c4e29-102">ICorDebugDebugEvent::Метод GetThread</span><span class="sxs-lookup"><span data-stu-id="c4e29-102">ICorDebugDebugEvent::GetThread Method</span></span>
<span data-ttu-id="c4e29-103">Получает поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="c4e29-103">Gets the thread on which the event occurred.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e29-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4e29-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e29-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4e29-105">Parameters</span></span>  
 <span data-ttu-id="c4e29-106">ppThread</span><span class="sxs-lookup"><span data-stu-id="c4e29-106">ppThread</span></span>  
 <span data-ttu-id="c4e29-107">[выходной] Указатель на адрес объекта ICorDebugThread, представляющего поток, в котором произошло событие.</span><span class="sxs-lookup"><span data-stu-id="c4e29-107">[out] A pointer to the address of an ICorDebugThread object that represents the thread on which the event occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e29-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="c4e29-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c4e29-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c4e29-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e29-110">Требования</span><span class="sxs-lookup"><span data-stu-id="c4e29-110">Requirements</span></span>  
 <span data-ttu-id="c4e29-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4e29-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e29-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c4e29-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c4e29-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4e29-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4e29-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e29-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e29-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c4e29-115">See also</span></span>

- [<span data-ttu-id="c4e29-116">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c4e29-116">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="c4e29-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c4e29-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
