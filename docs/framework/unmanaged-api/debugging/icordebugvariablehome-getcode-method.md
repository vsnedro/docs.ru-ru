---
title: 'Метод ICorDebugVariableHome:: с кодом'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetCode
helpviewer_keywords:
- ICorDebugVariableHome::GetCode method [.NET Framework debugging]
- GetCode method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: ef002890-4a7b-4a5d-abbf-16c60083f794
topic_type:
- apiref
ms.openlocfilehash: 6f5d99e6dc4290ef69c0a0748fe15ae538e83558
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684230"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="c65ef-102">Метод ICorDebugVariableHome:: с кодом</span><span class="sxs-lookup"><span data-stu-id="c65ef-102">ICorDebugVariableHome::GetCode Method</span></span>

<span data-ttu-id="c65ef-103">Возвращает экземпляр "ICorDebugCode", который содержит этот объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c65ef-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c65ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c65ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c65ef-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c65ef-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="c65ef-106">заполняет Указатель на адрес экземпляра ICorDebugCode, который содержит этот объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c65ef-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c65ef-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c65ef-107">Requirements</span></span>  

 <span data-ttu-id="c65ef-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c65ef-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c65ef-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c65ef-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c65ef-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c65ef-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c65ef-111">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c65ef-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c65ef-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c65ef-112">See also</span></span>

- [<span data-ttu-id="c65ef-113">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="c65ef-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
