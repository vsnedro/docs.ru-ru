---
title: Метод ICorDebugAppDomain::Attach
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.Attach
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::Attach
helpviewer_keywords:
- ICorDebugAppDomain::Attach method [.NET Framework debugging]
- Attach method [.NET Framework debugging]
ms.assetid: 0358b84a-4236-4c34-945b-4babff7df570
topic_type:
- apiref
ms.openlocfilehash: d133cacb611a1c7bd03d7653f46c2e5fb1acc043
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723354"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="1677d-102">Метод ICorDebugAppDomain::Attach</span><span class="sxs-lookup"><span data-stu-id="1677d-102">ICorDebugAppDomain::Attach Method</span></span>

<span data-ttu-id="1677d-103">Присоединяет отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="1677d-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1677d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1677d-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="1677d-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="1677d-105">Remarks</span></span>  

 <span data-ttu-id="1677d-106">Отладчик должен быть присоединен к домену приложения для получения событий и включения отладки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="1677d-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1677d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="1677d-107">Requirements</span></span>  

 <span data-ttu-id="1677d-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1677d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1677d-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1677d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1677d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1677d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1677d-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1677d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
