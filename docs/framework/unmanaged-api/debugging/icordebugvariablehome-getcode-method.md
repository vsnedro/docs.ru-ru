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
ms.openlocfilehash: 87d611a7b6e12a9238b00131326e8205778769e6
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396594"
---
# <a name="icordebugvariablehomegetcode-method"></a><span data-ttu-id="d3e77-102">Метод ICorDebugVariableHome:: с кодом</span><span class="sxs-lookup"><span data-stu-id="d3e77-102">ICorDebugVariableHome::GetCode Method</span></span>
<span data-ttu-id="d3e77-103">Возвращает экземпляр "ICorDebugCode", который содержит этот объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d3e77-103">Gets the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3e77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d3e77-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCode(  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3e77-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d3e77-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="d3e77-106">заполняет Указатель на адрес экземпляра ICorDebugCode, который содержит этот объект [ICorDebugVariableHome](icordebugvariablehome-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="d3e77-106">[out] A pointer to the address of the "ICorDebugCode" instance that contains this [ICorDebugVariableHome](icordebugvariablehome-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3e77-107">Требования</span><span class="sxs-lookup"><span data-stu-id="d3e77-107">Requirements</span></span>  
 <span data-ttu-id="d3e77-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3e77-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3e77-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3e77-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3e77-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3e77-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3e77-111">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3e77-111">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3e77-112">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d3e77-112">See also</span></span>

- [<span data-ttu-id="d3e77-113">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="d3e77-113">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
