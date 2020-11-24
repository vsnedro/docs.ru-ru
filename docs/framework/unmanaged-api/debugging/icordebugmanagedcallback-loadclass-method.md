---
title: Метод ICorDebugManagedCallback::LoadClass
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LoadClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LoadClass
helpviewer_keywords:
- ICorDebugManagedCallback::LoadClass method [.NET Framework debugging]
- LoadClass method [.NET Framework debugging]
ms.assetid: e58dac7b-85c3-41ca-b9aa-3a7fc9ae6680
topic_type:
- apiref
ms.openlocfilehash: 6f1672d40cd495d3ec099abc703639cf52460703
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679667"
---
# <a name="icordebugmanagedcallbackloadclass-method"></a><span data-ttu-id="723f3-102">Метод ICorDebugManagedCallback::LoadClass</span><span class="sxs-lookup"><span data-stu-id="723f3-102">ICorDebugManagedCallback::LoadClass Method</span></span>

<span data-ttu-id="723f3-103">Уведомляет отладчик о том, что класс был загружен.</span><span class="sxs-lookup"><span data-stu-id="723f3-103">Notifies the debugger that a class has been loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="723f3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="723f3-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadClass (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugClass     *c  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="723f3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="723f3-105">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="723f3-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, в который был загружен класс.</span><span class="sxs-lookup"><span data-stu-id="723f3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain into which the class has been loaded.</span></span>  
  
 `c`  
 <span data-ttu-id="723f3-107">окне Указатель на объект ICorDebugClass, представляющий класс.</span><span class="sxs-lookup"><span data-stu-id="723f3-107">[in] A pointer to an ICorDebugClass object that represents the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="723f3-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="723f3-108">Remarks</span></span>  

 <span data-ttu-id="723f3-109">Этот обратный вызов происходит, только если для модуля, содержащего класс, была включена загрузка класса.</span><span class="sxs-lookup"><span data-stu-id="723f3-109">This callback occurs only if class loading has been enabled for the module that contains the class.</span></span> <span data-ttu-id="723f3-110">Загрузка класса всегда включена для динамических модулей.</span><span class="sxs-lookup"><span data-stu-id="723f3-110">Class loading is always enabled for dynamic modules.</span></span>  
  
 <span data-ttu-id="723f3-111">`LoadClass`Обратный вызов предоставляет соответствующее время для привязки точек останова к вновь созданным классам в динамических модулях.</span><span class="sxs-lookup"><span data-stu-id="723f3-111">The `LoadClass` callback provides an appropriate time to bind breakpoints to newly generated classes in dynamic modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="723f3-112">Требования</span><span class="sxs-lookup"><span data-stu-id="723f3-112">Requirements</span></span>  

 <span data-ttu-id="723f3-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="723f3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="723f3-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="723f3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="723f3-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="723f3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="723f3-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="723f3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723f3-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="723f3-117">See also</span></span>

- [<span data-ttu-id="723f3-118">Метод UnloadClass</span><span class="sxs-lookup"><span data-stu-id="723f3-118">UnloadClass Method</span></span>](icordebugmanagedcallback-unloadclass-method.md)
- [<span data-ttu-id="723f3-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="723f3-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
