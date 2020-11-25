---
title: Метод ICorDebugModule::GetAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
ms.openlocfilehash: e0ae11ee24a5e25fb439d5c502c4cda5bcb6a80e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710276"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="4feeb-102">Метод ICorDebugModule::GetAssembly</span><span class="sxs-lookup"><span data-stu-id="4feeb-102">ICorDebugModule::GetAssembly Method</span></span>

<span data-ttu-id="4feeb-103">Возвращает содержащуюся сборку для этого модуля.</span><span class="sxs-lookup"><span data-stu-id="4feeb-103">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4feeb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4feeb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4feeb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4feeb-105">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="4feeb-106">заполняет Указатель на объект ICorDebugAssembly, представляющий сборку, содержащую этот модуль.</span><span class="sxs-lookup"><span data-stu-id="4feeb-106">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4feeb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="4feeb-107">Requirements</span></span>  

 <span data-ttu-id="4feeb-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4feeb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4feeb-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4feeb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4feeb-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4feeb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4feeb-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4feeb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
