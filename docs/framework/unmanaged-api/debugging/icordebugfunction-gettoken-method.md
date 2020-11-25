---
title: Метод ICorDebugFunction::GetToken
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetToken
helpviewer_keywords:
- ICorDebugFunction::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: c6bbf479-062e-48e9-9c70-0f92e293e36a
topic_type:
- apiref
ms.openlocfilehash: 9aee95c554afad5b2ea3cf157fc9e62c9b7e40e9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696119"
---
# <a name="icordebugfunctiongettoken-method"></a><span data-ttu-id="9fc3d-102">Метод ICorDebugFunction::GetToken</span><span class="sxs-lookup"><span data-stu-id="9fc3d-102">ICorDebugFunction::GetToken Method</span></span>

<span data-ttu-id="9fc3d-103">Возвращает маркер метаданных для этой функции.</span><span class="sxs-lookup"><span data-stu-id="9fc3d-103">Gets the metadata token for this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fc3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9fc3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken (  
    [out] mdMethodDef *pMethodDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fc3d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9fc3d-105">Parameters</span></span>  

 `pMethodDef`  
 <span data-ttu-id="9fc3d-106">заполняет Указатель на `mdMethodDef` маркер, который ссылается на метаданные для этой функции.</span><span class="sxs-lookup"><span data-stu-id="9fc3d-106">[out] A pointer to an `mdMethodDef` token that references the metadata for this function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fc3d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9fc3d-107">Requirements</span></span>  

 <span data-ttu-id="9fc3d-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fc3d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fc3d-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9fc3d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9fc3d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fc3d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fc3d-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fc3d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
