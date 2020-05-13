---
title: Метод ICorDebugModule::GetSize
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetSize method [.NET Framework debugging]
ms.assetid: 5c68375d-145d-46ef-a7c8-2dc4257472de
topic_type:
- apiref
ms.openlocfilehash: 4f9818137016dc3e0522ed516c52df2550ffdfca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212520"
---
# <a name="icordebugmodulegetsize-method"></a><span data-ttu-id="620de-102">Метод ICorDebugModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="620de-102">ICorDebugModule::GetSize Method</span></span>
<span data-ttu-id="620de-103">Возвращает размер модуля (в байтах).</span><span class="sxs-lookup"><span data-stu-id="620de-103">Gets the size, in bytes, of the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="620de-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="620de-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
    [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="620de-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="620de-105">Parameters</span></span>  
 `pcBytes`  
 <span data-ttu-id="620de-106">заполняет Размер модуля в байтах.</span><span class="sxs-lookup"><span data-stu-id="620de-106">[out] The size of the module in bytes.</span></span>  
  
 <span data-ttu-id="620de-107">Если модуль был создан из генератора образов в машинном кодах (NGen. exe), размер модуля будет равен нулю.</span><span class="sxs-lookup"><span data-stu-id="620de-107">If the module was produced from the native image generator (NGen.exe), the size of the module will be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="620de-108">Требования</span><span class="sxs-lookup"><span data-stu-id="620de-108">Requirements</span></span>  
 <span data-ttu-id="620de-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="620de-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="620de-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="620de-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="620de-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="620de-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="620de-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="620de-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
