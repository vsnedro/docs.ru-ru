---
title: Метод ICorDebugStringValue::GetString
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetString
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type:
- apiref
ms.openlocfilehash: 9c154d4ad561e0bd9d82adaca77d2e30f11a5237
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379667"
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="43a6d-102">Метод ICorDebugStringValue::GetString</span><span class="sxs-lookup"><span data-stu-id="43a6d-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="43a6d-103">Возвращает строку, на которую ссылается этот ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="43a6d-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43a6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43a6d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]
        WCHAR       szString[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43a6d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="43a6d-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="43a6d-106">[in] Размер массива `szString`.</span><span class="sxs-lookup"><span data-stu-id="43a6d-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="43a6d-107">заполняет Указатель на число символов, возвращаемых в `szString` массиве.</span><span class="sxs-lookup"><span data-stu-id="43a6d-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="43a6d-108">заполняет Массив, в котором хранится извлеченная строка.</span><span class="sxs-lookup"><span data-stu-id="43a6d-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43a6d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="43a6d-109">Requirements</span></span>  
 <span data-ttu-id="43a6d-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43a6d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43a6d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43a6d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43a6d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43a6d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43a6d-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43a6d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
