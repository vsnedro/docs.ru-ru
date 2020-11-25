---
title: Метод ICorDebugModuleEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugModuleEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleEnum::Next
helpviewer_keywords:
- ICorDebugModuleEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugModuleEnum interface [.NET Framework debugging]
ms.assetid: 9ff3fcd6-38fe-41f8-bfd3-f0ab6c7d77ca
topic_type:
- apiref
ms.openlocfilehash: a4bdac42c584d5d34b072354de65ed20c6a80609
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95709496"
---
# <a name="icordebugmoduleenumnext-method"></a><span data-ttu-id="5bc37-102">Метод ICorDebugModuleEnum::Next</span><span class="sxs-lookup"><span data-stu-id="5bc37-102">ICorDebugModuleEnum::Next Method</span></span>

<span data-ttu-id="5bc37-103">Возвращает количество экземпляров ICorDebugModule, заданных `celt` из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="5bc37-103">Gets the number of "ICorDebugModule" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bc37-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bc37-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugModule *modules[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bc37-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bc37-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5bc37-106">окне Число `ICorDebugModule` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="5bc37-106">[in] The number of `ICorDebugModule` instances to be retrieved.</span></span>  
  
 `modules`  
 <span data-ttu-id="5bc37-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugModule` объект.</span><span class="sxs-lookup"><span data-stu-id="5bc37-107">[out] An array of pointers, each of which points to an `ICorDebugModule` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5bc37-108">заполняет Указатель на число `ICorDebugModule` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="5bc37-108">[out] Pointer to the number of `ICorDebugModule` instances actually returned.</span></span> <span data-ttu-id="5bc37-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="5bc37-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bc37-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5bc37-110">Requirements</span></span>  

 <span data-ttu-id="5bc37-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bc37-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bc37-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5bc37-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5bc37-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bc37-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bc37-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bc37-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bc37-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5bc37-115">See also</span></span>
