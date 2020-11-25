---
title: Метод ICorDebugDebugEvent::GetEventKind
ms.date: 03/30/2017
ms.assetid: c37aaceb-c948-46bd-a943-08be4cbb76f4
ms.openlocfilehash: 7876dc6ec5ecee52b64e54e1c42533f8348e4dc4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713682"
---
# <a name="icordebugdebugeventgeteventkind-method"></a><span data-ttu-id="a833a-102">Метод ICorDebugDebugEvent::GetEventKind</span><span class="sxs-lookup"><span data-stu-id="a833a-102">ICorDebugDebugEvent::GetEventKind Method</span></span>

<span data-ttu-id="a833a-103">Указывает тип события, который представляет этот объект `ICorDebugDebugEvent`.</span><span class="sxs-lookup"><span data-stu-id="a833a-103">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a833a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a833a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetEventKind(  
    [out]CorDebugDebugEventKind *pDebugEventKind  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a833a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a833a-105">Parameters</span></span>  

 <span data-ttu-id="a833a-106">pDebugEventKind</span><span class="sxs-lookup"><span data-stu-id="a833a-106">pDebugEventKind</span></span>  
 <span data-ttu-id="a833a-107">Указатель на элемент перечисления [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) , указывающий тип события.</span><span class="sxs-lookup"><span data-stu-id="a833a-107">A pointer to a [CorDebugDebugEventKind](cordebugdebugeventkind-enumeration.md) enumeration member that indicates the type of event.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a833a-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="a833a-108">Remarks</span></span>  

 <span data-ttu-id="a833a-109">На основе значения `pDebugEventKind` можно вызвать `QueryInterface`, чтобы получить более точный интерфейс событий отладки, содержащий дополнительные данные.</span><span class="sxs-lookup"><span data-stu-id="a833a-109">Based on the value of `pDebugEventKind`, you can call `QueryInterface` to get a more precise debug event interface that has additional data.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a833a-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="a833a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a833a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="a833a-111">Requirements</span></span>  

 <span data-ttu-id="a833a-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a833a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a833a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a833a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a833a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a833a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a833a-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a833a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a833a-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a833a-116">See also</span></span>

- [<span data-ttu-id="a833a-117">Интерфейс ICorDebugDebugEvent</span><span class="sxs-lookup"><span data-stu-id="a833a-117">ICorDebugDebugEvent Interface</span></span>](icordebugdebugevent-interface.md)
- [<span data-ttu-id="a833a-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a833a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
