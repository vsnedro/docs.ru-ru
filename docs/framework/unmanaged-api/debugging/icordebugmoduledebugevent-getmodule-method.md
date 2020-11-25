---
title: Метод ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: ec23cda02ff689a3365fe96fb5280054a9795caa
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709509"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="66a12-102">Метод ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="66a12-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>

<span data-ttu-id="66a12-103">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="66a12-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66a12-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="66a12-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="66a12-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="66a12-105">Parameters</span></span>  

 `ppModule`  
 <span data-ttu-id="66a12-106">[out] Указатель на адрес объекта ICorDebugModule, представляющего объединенный модуль, который был только что загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="66a12-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66a12-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="66a12-107">Remarks</span></span>  

 <span data-ttu-id="66a12-108">Можно вызвать метод [GetEventKind](icordebugdebugevent-geteventkind-method.md) , чтобы определить, был ли модуль загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="66a12-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66a12-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="66a12-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="66a12-110">Требования</span><span class="sxs-lookup"><span data-stu-id="66a12-110">Requirements</span></span>  

 <span data-ttu-id="66a12-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="66a12-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="66a12-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="66a12-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="66a12-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="66a12-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="66a12-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="66a12-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66a12-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="66a12-115">See also</span></span>

- [<span data-ttu-id="66a12-116">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="66a12-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="66a12-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="66a12-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
