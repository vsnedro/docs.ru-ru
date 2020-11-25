---
title: Метод ICorDebugFunction::GetNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: e34dff2ebdb6e1ea56c2682b351c3e17a44416f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726318"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="7241d-102">Метод ICorDebugFunction::GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="7241d-102">ICorDebugFunction::GetNativeCode Method</span></span>

<span data-ttu-id="7241d-103">Возвращает машинный код для функции, представленной этим экземпляром ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="7241d-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7241d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7241d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7241d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7241d-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="7241d-106">заполняет Указатель на экземпляр ICorDebugCode, представляющий машинный код для этой функции, или значение null, если эта функция является кодом MSIL, который не был скомпилирован JIT-КОМПИЛЯТОРом.</span><span class="sxs-lookup"><span data-stu-id="7241d-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7241d-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="7241d-107">Remarks</span></span>  

 <span data-ttu-id="7241d-108">Если функция, представленная этим `ICorDebugFunction` экземпляром, скомпилирована JIT-компилятором более одного раза, как в случае универсальных типов, `GetNativeCode` возвращает произвольный объект машинного кода.</span><span class="sxs-lookup"><span data-stu-id="7241d-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7241d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7241d-109">Requirements</span></span>  

 <span data-ttu-id="7241d-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7241d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7241d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7241d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7241d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7241d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7241d-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7241d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
