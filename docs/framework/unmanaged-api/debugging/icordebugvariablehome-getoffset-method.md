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
ms.openlocfilehash: 75a165e2fd517f36d779a934a5bdd9c41956411a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396768"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="d14a4-102">Метод ICorDebugVariableHome:: методом offset</span><span class="sxs-lookup"><span data-stu-id="d14a4-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="d14a4-103">Возвращает смещение от базового регистра для переменной.</span><span class="sxs-lookup"><span data-stu-id="d14a4-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d14a4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d14a4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d14a4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d14a4-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="d14a4-106">заполняет Смещение от базового регистра.</span><span class="sxs-lookup"><span data-stu-id="d14a4-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d14a4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="d14a4-107">Return Value</span></span>  
 <span data-ttu-id="d14a4-108">Метод возвращает следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d14a4-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="d14a4-109">Значение</span><span class="sxs-lookup"><span data-stu-id="d14a4-109">Value</span></span>|<span data-ttu-id="d14a4-110">Описание</span><span class="sxs-lookup"><span data-stu-id="d14a4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="d14a4-111">Переменная находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="d14a4-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="d14a4-112">Переменная не находится в расположении в памяти относительно регистра.</span><span class="sxs-lookup"><span data-stu-id="d14a4-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d14a4-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d14a4-113">Requirements</span></span>  
 <span data-ttu-id="d14a4-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d14a4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d14a4-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d14a4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d14a4-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d14a4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d14a4-117">**.NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d14a4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14a4-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="d14a4-118">See also</span></span>

- [<span data-ttu-id="d14a4-119">Интерфейс ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="d14a4-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
