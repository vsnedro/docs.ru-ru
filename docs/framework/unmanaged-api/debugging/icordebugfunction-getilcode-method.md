---
title: Метод ICorDebugFunction::GetILCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
ms.openlocfilehash: b7d3fbafaab6d43fa89d45855628dbd6b9ab81e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696223"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="9277c-102">Метод ICorDebugFunction::GetILCode</span><span class="sxs-lookup"><span data-stu-id="9277c-102">ICorDebugFunction::GetILCode Method</span></span>

<span data-ttu-id="9277c-103">Возвращает экземпляр ICorDebugCode, представляющий код на языке MSIL, связанный с данным объектом ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="9277c-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9277c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9277c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9277c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9277c-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="9277c-106">заполняет Указатель на `ICorDebugCode` экземпляр или значение null, если функция не была скомпилирована в MSIL.</span><span class="sxs-lookup"><span data-stu-id="9277c-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9277c-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9277c-107">Remarks</span></span>  

 <span data-ttu-id="9277c-108">Если функция "изменить и продолжить" была разрешена для этой функции, метод получит `GetILCode` код MSIL, соответствующий измененной версии кода этой функции в общеязыковой среде выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="9277c-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9277c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9277c-109">Requirements</span></span>  

 <span data-ttu-id="9277c-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9277c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9277c-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9277c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9277c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9277c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9277c-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9277c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
