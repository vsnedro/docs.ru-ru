---
title: Метод ICorDebugStepper::SetRangeIL
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 5a27f155021661022b27022bbb252e00dfa67255
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95698784"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="a48db-102">Метод ICorDebugStepper::SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="a48db-102">ICorDebugStepper::SetRangeIL Method</span></span>

<span data-ttu-id="a48db-103">Задает значение, указывающее, будут ли вызовы метода [ICorDebugStepper:: степранже](icordebugstepper-steprange-method.md) передавать значения аргумента, которые относятся к машинному коду или по коду языка MSIL в методе, через который выполняется пошаговое выполнение.</span><span class="sxs-lookup"><span data-stu-id="a48db-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a48db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a48db-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a48db-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a48db-105">Parameters</span></span>  

 `bIL`  
 <span data-ttu-id="a48db-106">окне Задайте значение, `true` чтобы указать, что диапазоны зависят от кода MSIL.</span><span class="sxs-lookup"><span data-stu-id="a48db-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="a48db-107">Задайте значение, `false` чтобы указать, что диапазоны зависят от машинного кода.</span><span class="sxs-lookup"><span data-stu-id="a48db-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="a48db-108">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="a48db-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a48db-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a48db-109">Requirements</span></span>  

 <span data-ttu-id="a48db-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a48db-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a48db-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a48db-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a48db-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a48db-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a48db-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a48db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
