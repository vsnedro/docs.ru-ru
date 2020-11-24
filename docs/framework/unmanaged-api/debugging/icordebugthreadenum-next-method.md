---
title: Метод ICorDebugThreadEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugThreadEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThreadEnum::Next
helpviewer_keywords:
- ICorDebugThreadEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugThreadEnum interface [.NET Framework debugging]
ms.assetid: f967c93d-9a7f-4aaf-99a1-a1317899ff3f
topic_type:
- apiref
ms.openlocfilehash: 226b386c7a38c9a0b28b3bcc0420d14f6f4f4e7c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678432"
---
# <a name="icordebugthreadenumnext-method"></a><span data-ttu-id="8058a-102">Метод ICorDebugThreadEnum::Next</span><span class="sxs-lookup"><span data-stu-id="8058a-102">ICorDebugThreadEnum::Next Method</span></span>

<span data-ttu-id="8058a-103">Возвращает число указанных экземпляров ICorDebugThread из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="8058a-103">Gets the number of specified ICorDebugThread instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8058a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8058a-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugThread *threads[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8058a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8058a-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="8058a-106">окне Число `ICorDebugThread` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8058a-106">[in] The number of `ICorDebugThread` instances to be retrieved.</span></span>  
  
 `threads`  
 <span data-ttu-id="8058a-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugThread` объект, представляющий поток.</span><span class="sxs-lookup"><span data-stu-id="8058a-107">[out] An array of pointers, each of which points to an `ICorDebugThread` object that represents a thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8058a-108">заполняет Указатель на число `ICorDebugThread` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="8058a-108">[out] Pointer to the number of `ICorDebugThread` instances actually returned.</span></span> <span data-ttu-id="8058a-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="8058a-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8058a-110">Требования</span><span class="sxs-lookup"><span data-stu-id="8058a-110">Requirements</span></span>  

 <span data-ttu-id="8058a-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8058a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8058a-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8058a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8058a-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8058a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8058a-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8058a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
