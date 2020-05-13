---
title: Метод ICorDebugILFrame::CanSetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
ms.openlocfilehash: 2bd4ab4a080461c56b0287d24aa288847445d803
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210323"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="3e9b2-102">Метод ICorDebugILFrame::CanSetIP</span><span class="sxs-lookup"><span data-stu-id="3e9b2-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="3e9b2-103">Возвращает значение HRESULT, указывающее, безопасно ли устанавливать указатель инструкции в указанном расположении смещения в коде на языке MSIL.</span><span class="sxs-lookup"><span data-stu-id="3e9b2-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e9b2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e9b2-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e9b2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e9b2-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="3e9b2-106">окне Требуемый параметр для указателя инструкции.</span><span class="sxs-lookup"><span data-stu-id="3e9b2-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e9b2-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="3e9b2-107">Remarks</span></span>  
 <span data-ttu-id="3e9b2-108">Используйте `CanSetIP` метод перед вызовом метода [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3e9b2-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="3e9b2-109">Если `CanSetIP` возвращает любое значение HRESULT, отличное от S_OK, можно по-прежнему вызывать `ICorDebugILFrame::SetIP` , но не существует гарантии того, что отладчик продолжит безопасность и правильное выполнение отлаживаемого кода.</span><span class="sxs-lookup"><span data-stu-id="3e9b2-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e9b2-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3e9b2-110">Requirements</span></span>  
 <span data-ttu-id="3e9b2-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e9b2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e9b2-112">**Заголовок:** CorDebug. idl, CorDebug, h</span><span class="sxs-lookup"><span data-stu-id="3e9b2-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="3e9b2-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e9b2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e9b2-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e9b2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
