---
title: Метод ICorDebugAppDomain::IsAttached
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.IsAttached
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::IsAttached
helpviewer_keywords:
- IsAttached method [.NET Framework debugging]
- ICorDebugAppDomain::IsAttached method [.NET Framework debugging]
ms.assetid: af0c67c7-f53e-47c9-b84b-be50bd04903e
topic_type:
- apiref
ms.openlocfilehash: 898398b731832e698a43eb270bbdc63bb3867bb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702177"
---
# <a name="icordebugappdomainisattached-method"></a><span data-ttu-id="c14c0-102">Метод ICorDebugAppDomain::IsAttached</span><span class="sxs-lookup"><span data-stu-id="c14c0-102">ICorDebugAppDomain::IsAttached Method</span></span>

<span data-ttu-id="c14c0-103">Возвращает значение, указывающее, присоединен ли отладчик к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="c14c0-103">Gets a value that indicates whether the debugger is attached to the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c14c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c14c0-104">Syntax</span></span>  
  
```cpp  
HRESULT IsAttached (  
    [out] BOOL  *pbAttached  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c14c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c14c0-105">Parameters</span></span>  

 `pbAttached`  
 <span data-ttu-id="c14c0-106">[out] `true` значение, если отладчик присоединен к домену приложения; в противном случае — `false` .</span><span class="sxs-lookup"><span data-stu-id="c14c0-106">[out] `true` if the debugger is attached to the application domain; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c14c0-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c14c0-107">Remarks</span></span>  

 <span data-ttu-id="c14c0-108">Методы ICorDebugController нельзя использовать до тех пор, пока отладчик не подключится к домену приложения.</span><span class="sxs-lookup"><span data-stu-id="c14c0-108">The ICorDebugController methods cannot be used until the debugger attaches to the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c14c0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c14c0-109">Requirements</span></span>  

 <span data-ttu-id="c14c0-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c14c0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c14c0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c14c0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c14c0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c14c0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c14c0-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c14c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
