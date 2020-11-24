---
title: Метод ICorDebugFrame::GetFunctionToken
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunctionToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type:
- apiref
ms.openlocfilehash: 3430c5062bd5633e1178226974b7358783192e51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675988"
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="e322a-102">Метод ICorDebugFrame::GetFunctionToken</span><span class="sxs-lookup"><span data-stu-id="e322a-102">ICorDebugFrame::GetFunctionToken Method</span></span>

<span data-ttu-id="e322a-103">Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="e322a-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e322a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e322a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e322a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e322a-105">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="e322a-106">заполняет Указатель на `mdMethodDef` маркер, который ссылается на метаданные функции.</span><span class="sxs-lookup"><span data-stu-id="e322a-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e322a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e322a-107">Requirements</span></span>  

 <span data-ttu-id="e322a-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e322a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e322a-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e322a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e322a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e322a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e322a-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e322a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
