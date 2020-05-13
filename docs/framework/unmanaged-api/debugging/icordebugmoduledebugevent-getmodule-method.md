---
title: Метод ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 1df71ddbf1ee76cc8202d8f9e263b9d95b4aaa09
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213365"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a><span data-ttu-id="bf723-102">Метод ICorDebugModuleDebugEvent::GetModule</span><span class="sxs-lookup"><span data-stu-id="bf723-102">ICorDebugModuleDebugEvent::GetModule Method</span></span>
<span data-ttu-id="bf723-103">Возвращает объединенный модуль, который только что был загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="bf723-103">Gets the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf723-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf723-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf723-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bf723-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="bf723-106">[out] Указатель на адрес объекта ICorDebugModule, представляющего объединенный модуль, который был только что загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="bf723-106">[out] A pointer to the address of an ICorDebugModule object that represents the merged module that was just loaded or unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf723-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="bf723-107">Remarks</span></span>  
 <span data-ttu-id="bf723-108">Можно вызвать метод [GetEventKind](icordebugdebugevent-geteventkind-method.md) , чтобы определить, был ли модуль загружен или выгружен.</span><span class="sxs-lookup"><span data-stu-id="bf723-108">You can call the [GetEventKind](icordebugdebugevent-geteventkind-method.md) method to determine whether the module was loaded or unloaded.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf723-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="bf723-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf723-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bf723-110">Requirements</span></span>  
 <span data-ttu-id="bf723-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf723-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf723-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf723-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf723-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf723-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf723-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf723-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf723-115">См. также</span><span class="sxs-lookup"><span data-stu-id="bf723-115">See also</span></span>

- [<span data-ttu-id="bf723-116">Интерфейс ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="bf723-116">ICorDebugModuleDebugEvent Interface</span></span>](icordebugmoduledebugevent-interface.md)
- [<span data-ttu-id="bf723-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="bf723-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
