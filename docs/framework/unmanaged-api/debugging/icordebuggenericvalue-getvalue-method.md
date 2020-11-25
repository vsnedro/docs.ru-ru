---
title: Метод ICorDebugGenericValue::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue::GetValue
helpviewer_keywords:
- ICorDebugGenericValue::GetValue method [.NET Framework debugging]
- GetValue method, ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: 4e95d7cb-144d-4ccf-8a69-d605f4744be2
topic_type:
- apiref
ms.openlocfilehash: dd1c1ba4a976a10d0c38c5295fff838faf072f51
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728112"
---
# <a name="icordebuggenericvaluegetvalue-method"></a><span data-ttu-id="892a8-102">Метод ICorDebugGenericValue::GetValue</span><span class="sxs-lookup"><span data-stu-id="892a8-102">ICorDebugGenericValue::GetValue Method</span></span>

<span data-ttu-id="892a8-103">Копирует значение этого универсального объекта в указанный буфер.</span><span class="sxs-lookup"><span data-stu-id="892a8-103">Copies the value of this generic into the specified buffer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="892a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="892a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetValue (  
    [out] void     *pTo  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="892a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="892a8-105">Parameters</span></span>  

 `pTo`  
 <span data-ttu-id="892a8-106">заполняет Указатель на значение, представленное этим объектом ICorDebugGenericValue.</span><span class="sxs-lookup"><span data-stu-id="892a8-106">[out] A pointer to the value that is represented by this ICorDebugGenericValue object.</span></span> <span data-ttu-id="892a8-107">Значение может быть простым типом или ссылочным типом (т. е. указателем).</span><span class="sxs-lookup"><span data-stu-id="892a8-107">The value may be a simple type or a reference type (that is, a pointer).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="892a8-108">Требования</span><span class="sxs-lookup"><span data-stu-id="892a8-108">Requirements</span></span>  

 <span data-ttu-id="892a8-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="892a8-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="892a8-110">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="892a8-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="892a8-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="892a8-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="892a8-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="892a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
