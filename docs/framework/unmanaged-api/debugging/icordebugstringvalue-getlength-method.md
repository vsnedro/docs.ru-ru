---
title: Метод ICorDebugStringValue::GetLength
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue.GetLength
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue::GetLength
helpviewer_keywords:
- ICorDebugStringValue::GetLength method [.NET Framework debugging]
- GetLength method [.NET Framework debugging]
ms.assetid: a1ebfc69-46a6-4225-8788-b7cfb2f15e1d
topic_type:
- apiref
ms.openlocfilehash: 945e4ac88634c9103a722a180a4fe92a554ca53b
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378896"
---
# <a name="icordebugstringvaluegetlength-method"></a><span data-ttu-id="967d1-102">Метод ICorDebugStringValue::GetLength</span><span class="sxs-lookup"><span data-stu-id="967d1-102">ICorDebugStringValue::GetLength Method</span></span>
<span data-ttu-id="967d1-103">Возвращает число символов в строке, на которую ссылается этот ICorDebugStringValue.</span><span class="sxs-lookup"><span data-stu-id="967d1-103">Gets the number of characters in the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="967d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="967d1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLength (  
    [out] ULONG32   *pcchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="967d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="967d1-105">Parameters</span></span>  
 `pcchString`  
 <span data-ttu-id="967d1-106">заполняет Указатель на значение, указывающее длину строки, на которую ссылается этот `ICorDebugStringValue` объект.</span><span class="sxs-lookup"><span data-stu-id="967d1-106">[out] A pointer to a value that specifies the length of the string referenced by this `ICorDebugStringValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="967d1-107">Требования</span><span class="sxs-lookup"><span data-stu-id="967d1-107">Requirements</span></span>  
 <span data-ttu-id="967d1-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="967d1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="967d1-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="967d1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="967d1-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="967d1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="967d1-111">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="967d1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
