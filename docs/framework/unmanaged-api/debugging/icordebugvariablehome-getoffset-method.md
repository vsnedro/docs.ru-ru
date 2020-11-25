---
title: 'Метод ICorDebugVariableHome:: методом offset'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: c5d491b66e4ec64dffa4e19dabff876c9c473036
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711797"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="c89fe-102">Метод ICorDebugVariableHome:: методом offset</span><span class="sxs-lookup"><span data-stu-id="c89fe-102">ICorDebugVariableHome::GetOffset Method</span></span>

<span data-ttu-id="c89fe-103">Возвращает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="c89fe-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c89fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c89fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c89fe-105">Parameters</span></span>  

 `pOffset`  
 <span data-ttu-id="c89fe-106">заполняет Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="c89fe-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c89fe-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c89fe-107">Return Value</span></span>  

 <span data-ttu-id="c89fe-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c89fe-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="c89fe-109">Значение</span><span class="sxs-lookup"><span data-stu-id="c89fe-109">Value</span></span>|<span data-ttu-id="c89fe-110">Описание</span><span class="sxs-lookup"><span data-stu-id="c89fe-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="c89fe-111">Переменная находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="c89fe-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="c89fe-112">Переменная не находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="c89fe-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c89fe-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c89fe-113">Requirements</span></span>  

 <span data-ttu-id="c89fe-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c89fe-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c89fe-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c89fe-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c89fe-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c89fe-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c89fe-117">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c89fe-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c89fe-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c89fe-118">See also</span></span>

- [<span data-ttu-id="c89fe-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="c89fe-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
