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
ms.openlocfilehash: 92cc6c3ce15d8391a43ff130a82476a4363ff5bd
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895299"
---
# <a name="icordebugappdomainattach-method"></a><span data-ttu-id="c155e-102">Метод ICorDebugAppDomain::Attach</span><span class="sxs-lookup"><span data-stu-id="c155e-102">ICorDebugAppDomain::Attach Method</span></span>
<span data-ttu-id="c155e-103">Присоединяет отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="c155e-103">Attaches the debugger to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c155e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c155e-104">Syntax</span></span>  
  
```cpp  
HRESULT Attach ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c155e-105">Remarks</span><span class="sxs-lookup"><span data-stu-id="c155e-105">Remarks</span></span>  
 <span data-ttu-id="c155e-106">Отладчик должен быть присоединен к домену приложения для получения событий и включения отладки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="c155e-106">The debugger must be attached to the application domain to receive events and to enable debugging of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c155e-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c155e-107">Requirements</span></span>  
 <span data-ttu-id="c155e-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c155e-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c155e-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c155e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c155e-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c155e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c155e-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c155e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
