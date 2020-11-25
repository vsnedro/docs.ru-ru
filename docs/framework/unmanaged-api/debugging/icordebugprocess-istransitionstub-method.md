---
title: Метод ICorDebugProcess::IsTransitionStub
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: 2996c219ccf4e975c45fb531807abc4a608bae73
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694780"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="49370-102">Метод ICorDebugProcess::IsTransitionStub</span><span class="sxs-lookup"><span data-stu-id="49370-102">ICorDebugProcess::IsTransitionStub Method</span></span>

<span data-ttu-id="49370-103">Возвращает значение, указывающее, находится ли адрес в заглушке, что приведет к переходу в управляемый код.</span><span class="sxs-lookup"><span data-stu-id="49370-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49370-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="49370-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49370-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="49370-105">Parameters</span></span>  

 `address`  
 <span data-ttu-id="49370-106">окне `CORDB_ADDRESS` Значение, указывающее рассматриваемый адрес.</span><span class="sxs-lookup"><span data-stu-id="49370-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="49370-107">заполняет Указатель на логическое значение, равное, `true` если указанный адрес находится внутри заглушки, которая приведет к переходу в управляемый код; в противном случае `pbTransitionStub` — \* `false` .</span><span class="sxs-lookup"><span data-stu-id="49370-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="49370-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="49370-108">Remarks</span></span>  

 <span data-ttu-id="49370-109">`IsTransitionStub`Метод может использоваться неуправляемым кодом пошагового выполнения, чтобы решить, когда следует возвращать контроль пошагового выполнения в управляемое средство Организации.</span><span class="sxs-lookup"><span data-stu-id="49370-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="49370-110">Вы также можете идентифицировать заглушки перехода, просмотрев информацию в переносимом исполняемом файле (PE).</span><span class="sxs-lookup"><span data-stu-id="49370-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49370-111">Требования</span><span class="sxs-lookup"><span data-stu-id="49370-111">Requirements</span></span>  

 <span data-ttu-id="49370-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49370-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49370-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49370-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49370-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49370-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49370-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49370-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
