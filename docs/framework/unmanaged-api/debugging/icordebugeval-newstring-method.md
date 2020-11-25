---
title: Метод ICorDebugEval::NewString
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewString
helpviewer_keywords:
- NewString method [.NET Framework debugging]
- ICorDebugEval::NewString method [.NET Framework debugging]
ms.assetid: 29e7a14b-d50e-4852-bfda-011b76c0c9ee
topic_type:
- apiref
ms.openlocfilehash: c2d29a0cc344539bf515793c071fe839aa441ebc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729737"
---
# <a name="icordebugevalnewstring-method"></a><span data-ttu-id="6f229-102">Метод ICorDebugEval::NewString</span><span class="sxs-lookup"><span data-stu-id="6f229-102">ICorDebugEval::NewString Method</span></span>

<span data-ttu-id="6f229-103">Выделяет новый экземпляр строки с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="6f229-103">Allocates a new string instance with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f229-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f229-104">Syntax</span></span>  
  
```cpp  
HRESULT NewString (  
    [in] LPCWSTR   string  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f229-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f229-105">Parameters</span></span>  

 `string`  
 <span data-ttu-id="6f229-106">окне Указатель на содержимое строки.</span><span class="sxs-lookup"><span data-stu-id="6f229-106">[in] Pointer to the contents for the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f229-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6f229-107">Remarks</span></span>  

 <span data-ttu-id="6f229-108">Строка всегда создается в домене приложения, в котором в данный момент выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="6f229-108">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f229-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6f229-109">Requirements</span></span>  

 <span data-ttu-id="6f229-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f229-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f229-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f229-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f229-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f229-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f229-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f229-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
