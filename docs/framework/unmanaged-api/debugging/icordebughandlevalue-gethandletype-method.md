---
title: Метод ICorDebugHandleValue::GetHandleType
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue.GetHandleType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue::GetHandleType
helpviewer_keywords:
- GetHandleType method [.NET Framework debugging]
- ICorDebugHandleValue::GetHandleType method [.NET Framework debugging]
ms.assetid: d5e7b12d-835a-4e86-ae2f-d658d4f1c67c
topic_type:
- apiref
ms.openlocfilehash: 72ef9a0fe4cd08ce67594600375953c249243d4f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734157"
---
# <a name="icordebughandlevaluegethandletype-method"></a><span data-ttu-id="3c4d2-102">Метод ICorDebugHandleValue::GetHandleType</span><span class="sxs-lookup"><span data-stu-id="3c4d2-102">ICorDebugHandleValue::GetHandleType Method</span></span>

<span data-ttu-id="3c4d2-103">Возвращает значение, указывающее тип маркера, на который ссылается этот объект ICorDebugHandleValue.</span><span class="sxs-lookup"><span data-stu-id="3c4d2-103">Gets a value that indicates the kind of handle referenced by this ICorDebugHandleValue object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c4d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c4d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHandleType (  
    [out] CorDebugHandleType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c4d2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c4d2-105">Parameters</span></span>  

 `pType`  
 <span data-ttu-id="3c4d2-106">заполняет Указатель на значение перечисления Кордебугхандлетипе, указывающее тип этого маркера.</span><span class="sxs-lookup"><span data-stu-id="3c4d2-106">[out] A pointer to a value of the CorDebugHandleType enumeration that indicates the type of this handle.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c4d2-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3c4d2-107">Requirements</span></span>  

 <span data-ttu-id="3c4d2-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c4d2-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c4d2-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c4d2-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c4d2-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c4d2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c4d2-111">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c4d2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
