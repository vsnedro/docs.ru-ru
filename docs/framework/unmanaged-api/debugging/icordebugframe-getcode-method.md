---
title: Метод ICorDebugFrame::GetCode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCode
helpviewer_keywords:
- GetCode method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetCode method [.NET Framework debugging]
ms.assetid: fbaa0794-a031-4015-8beb-2749e47ac340
topic_type:
- apiref
ms.openlocfilehash: 29dc87bf465fc9751b5af795f7640b095e535e63
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95690399"
---
# <a name="icordebugframegetcode-method"></a><span data-ttu-id="a6f04-102">Метод ICorDebugFrame::GetCode</span><span class="sxs-lookup"><span data-stu-id="a6f04-102">ICorDebugFrame::GetCode Method</span></span>

<span data-ttu-id="a6f04-103">Возвращает указатель на код, связанный с этим кадром стека.</span><span class="sxs-lookup"><span data-stu-id="a6f04-103">Gets a pointer to the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f04-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6f04-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode (  
    [out] ICorDebugCode      **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6f04-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6f04-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="a6f04-106">заполняет Указатель на адрес объекта ICorDebugCode, представляющий код, связанный с этим кадром.</span><span class="sxs-lookup"><span data-stu-id="a6f04-106">[out] A pointer to the address of an ICorDebugCode object that represents the code associated with this frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f04-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a6f04-107">Requirements</span></span>  

 <span data-ttu-id="a6f04-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6f04-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f04-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6f04-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6f04-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f04-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f04-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f04-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
