---
title: Метод ICorDebugEval2::NewStringWithLength
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewStringWithLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewStringWithLength
helpviewer_keywords:
- NewStringWithLength method [.NET Framework debugging]
- ICorDebugEval2::NewStringWithLength method [.NET Framework debugging]
ms.assetid: d5f54a34-6335-4708-b407-a756ec70fab4
topic_type:
- apiref
ms.openlocfilehash: a2b76cb59a95082e0cf9c0884b8277cca3c8fe8d
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976074"
---
# <a name="icordebugeval2newstringwithlength-method"></a><span data-ttu-id="b35ee-102">Метод ICorDebugEval2::NewStringWithLength</span><span class="sxs-lookup"><span data-stu-id="b35ee-102">ICorDebugEval2::NewStringWithLength Method</span></span>
<span data-ttu-id="b35ee-103">Создает строку указанной длины с указанным содержимым.</span><span class="sxs-lookup"><span data-stu-id="b35ee-103">Creates a string of the specified length, with the specified contents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b35ee-104">Syntax</span></span>  
  
```cpp  
HRESULT NewStringWithLength (  
    [in] LPCWSTR               string,  
    [in] UINT                  uiLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b35ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b35ee-105">Parameters</span></span>  
 `string`  
 <span data-ttu-id="b35ee-106">окне Указатель на строковое значение.</span><span class="sxs-lookup"><span data-stu-id="b35ee-106">[in] A pointer to the string value.</span></span>  
  
 `uiLength`  
 <span data-ttu-id="b35ee-107">окне Длина строки.</span><span class="sxs-lookup"><span data-stu-id="b35ee-107">[in] Length of the string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b35ee-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="b35ee-108">Remarks</span></span>  
 <span data-ttu-id="b35ee-109">Если конечный нуль-символ строки должен быть в управляемой строке, вызывающий `NewStringWithLength` метод должен обеспечить, чтобы длина строки включала завершающий нуль-символ.</span><span class="sxs-lookup"><span data-stu-id="b35ee-109">If the string's trailing null character is expected to be in the managed string, the caller of the `NewStringWithLength` method must ensure that the string length includes the trailing null character.</span></span>  
  
 <span data-ttu-id="b35ee-110">Строка всегда создается в домене приложения, в котором в данный момент выполняется поток.</span><span class="sxs-lookup"><span data-stu-id="b35ee-110">The string is always created in the application domain in which the thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35ee-111">Требования</span><span class="sxs-lookup"><span data-stu-id="b35ee-111">Requirements</span></span>  
 <span data-ttu-id="b35ee-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b35ee-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b35ee-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b35ee-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b35ee-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b35ee-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b35ee-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b35ee-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
