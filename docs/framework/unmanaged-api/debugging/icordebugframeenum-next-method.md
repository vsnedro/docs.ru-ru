---
title: Метод ICorDebugFrameEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugFrameEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrameEnum::Next
helpviewer_keywords:
- ICorDebugFrameEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugFrameEnum interface [.NET Framework debugging]
ms.assetid: 0bc96acb-6179-4328-a447-cda562ce9e98
topic_type:
- apiref
ms.openlocfilehash: 76b96dfd9d22c7e770671dcc01cb421430df729f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728190"
---
# <a name="icordebugframeenumnext-method"></a><span data-ttu-id="cdb0d-102">Метод ICorDebugFrameEnum::Next</span><span class="sxs-lookup"><span data-stu-id="cdb0d-102">ICorDebugFrameEnum::Next Method</span></span>

<span data-ttu-id="cdb0d-103">Возвращает указанное число экземпляров ICorDebugFrame, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="cdb0d-103">Gets the specified number of ICorDebugFrame instances, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdb0d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cdb0d-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugFrame *frames[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdb0d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cdb0d-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="cdb0d-106">окне Число `ICorDebugFrame` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="cdb0d-106">[in] The number of `ICorDebugFrame` instances to be retrieved.</span></span>  
  
 `frames`  
 <span data-ttu-id="cdb0d-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugFrame` объект.</span><span class="sxs-lookup"><span data-stu-id="cdb0d-107">[out] An array of pointers, each of which points to an `ICorDebugFrame` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="cdb0d-108">заполняет Указатель на число `ICorDebugFrame` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="cdb0d-108">[out] A pointer to the number of `ICorDebugFrame` instances actually returned.</span></span> <span data-ttu-id="cdb0d-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="cdb0d-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdb0d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="cdb0d-110">Requirements</span></span>  

 <span data-ttu-id="cdb0d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdb0d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdb0d-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cdb0d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cdb0d-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cdb0d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cdb0d-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdb0d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
