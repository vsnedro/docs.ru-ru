---
title: Метод ICorDebugThread::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateStepper
helpviewer_keywords:
- ICorDebugThread::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 4657443f-dd12-431b-a648-175c23f13c83
topic_type:
- apiref
ms.openlocfilehash: dcaa5adc41a9e451b123b088dd900f01d9161689
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688280"
---
# <a name="icordebugthreadcreatestepper-method"></a><span data-ttu-id="44187-102">Метод ICorDebugThread::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="44187-102">ICorDebugThread::CreateStepper Method</span></span>

<span data-ttu-id="44187-103">Создает объект ICorDebugStepper, позволяющий выполнять пошаговую отладку активной рамки этого ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="44187-103">Creates an ICorDebugStepper object that allows stepping through the active frame of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44187-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44187-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44187-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="44187-105">Parameters</span></span>  

 `ppStepper`  
 <span data-ttu-id="44187-106">заполняет Указатель на адрес `ICorDebugStepper` объекта, который допускает пошаговое выполнение активного кадра этого потока.</span><span class="sxs-lookup"><span data-stu-id="44187-106">[out] A pointer to the address of an `ICorDebugStepper` object that allows stepping through the active frame of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44187-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="44187-107">Remarks</span></span>  

 <span data-ttu-id="44187-108">Активным кадром может быть неуправляемый код.</span><span class="sxs-lookup"><span data-stu-id="44187-108">The active frame may be unmanaged code.</span></span>  
  
 <span data-ttu-id="44187-109">`ICorDebugStepper`Для выполнения фактического пошагового шага необходимо использовать интерфейс.</span><span class="sxs-lookup"><span data-stu-id="44187-109">The `ICorDebugStepper` interface must be used to perform the actual stepping.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44187-110">Требования</span><span class="sxs-lookup"><span data-stu-id="44187-110">Requirements</span></span>  

 <span data-ttu-id="44187-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44187-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44187-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44187-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="44187-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44187-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44187-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44187-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
