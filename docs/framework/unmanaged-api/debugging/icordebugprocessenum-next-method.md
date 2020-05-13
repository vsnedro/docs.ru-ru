---
title: Метод ICorDebugProcessEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugProcessEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcessEnum::Next
helpviewer_keywords:
- Next method, ICorDebugProcessEnum interface [.NET Framework debugging]
- ICorDebugProcessEnum::Next method [.NET Framework debugging]
ms.assetid: 4ac7077c-8d88-49c4-b360-b3af0c541c63
topic_type:
- apiref
ms.openlocfilehash: d00a5f71ac7e47d78deebca0e46350e465964c72
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210102"
---
# <a name="icordebugprocessenumnext-method"></a><span data-ttu-id="177a8-102">Метод ICorDebugProcessEnum::Next</span><span class="sxs-lookup"><span data-stu-id="177a8-102">ICorDebugProcessEnum::Next Method</span></span>
<span data-ttu-id="177a8-103">Возвращает указанное число экземпляров ICorDebugProcess из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="177a8-103">Gets the specified number of ICorDebugProcess instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="177a8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="177a8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in]  ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugProcess *processes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="177a8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="177a8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="177a8-106">окне Число `ICorDebugProcess` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="177a8-106">[in] The number of `ICorDebugProcess` instances to be retrieved.</span></span>  
  
 `processes`  
 <span data-ttu-id="177a8-107">заполняет Массив указателей, каждый из которых указывает на `ICorDebugProcess` объект, представляющий процесс.</span><span class="sxs-lookup"><span data-stu-id="177a8-107">[out] An array of pointers, each of which points to an `ICorDebugProcess` object that represents a process.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="177a8-108">заполняет Указатель на число `ICorDebugProcess` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="177a8-108">[out] Pointer to the number of `ICorDebugProcess` instances actually returned.</span></span> <span data-ttu-id="177a8-109">Это значение может быть равно NULL `celt` , если равно единице.</span><span class="sxs-lookup"><span data-stu-id="177a8-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="177a8-110">Требования</span><span class="sxs-lookup"><span data-stu-id="177a8-110">Requirements</span></span>  
 <span data-ttu-id="177a8-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="177a8-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="177a8-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="177a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="177a8-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="177a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="177a8-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="177a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
