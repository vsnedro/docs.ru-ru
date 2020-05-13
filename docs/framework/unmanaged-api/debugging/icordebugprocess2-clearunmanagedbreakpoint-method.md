---
title: Метод ICorDebugProcess2::ClearUnmanagedBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.ClearUnmanagedBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::ClearUnmanagedBreakpoint
helpviewer_keywords:
- ClearUnmanagedBreakpoint method [.NET Framework debugging]
- ICorDebugProcess2::ClearUnmanagedBreakpoint method [.NET Framework debugging]
ms.assetid: 12ed0fff-7f0e-4d7a-bb70-b3376371f36c
topic_type:
- apiref
ms.openlocfilehash: 2b228383c3b393fe43f60d39e59cca37af36233f
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212496"
---
# <a name="icordebugprocess2clearunmanagedbreakpoint-method"></a><span data-ttu-id="5da5a-102">Метод ICorDebugProcess2::ClearUnmanagedBreakpoint</span><span class="sxs-lookup"><span data-stu-id="5da5a-102">ICorDebugProcess2::ClearUnmanagedBreakpoint Method</span></span>
<span data-ttu-id="5da5a-103">Удаляет ранее установленную точку останова по указанному адресу.</span><span class="sxs-lookup"><span data-stu-id="5da5a-103">Removes a previously set breakpoint at the given address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5da5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5da5a-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearUnmanagedBreakpoint (  
    [in] CORDB_ADDRESS   address  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5da5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5da5a-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5da5a-106">окне `CORDB_ADDRESS`Значение типа, указывающее адрес, по которому была задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="5da5a-106">[in] A `CORDB_ADDRESS` value that specifies the address at which the breakpoint was set.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5da5a-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5da5a-107">Remarks</span></span>  
 <span data-ttu-id="5da5a-108">Указанная точка останова была ранее задана предыдущим вызовом метода [ICorDebugProcess2:: сетунманажедбреакпоинт](icordebugprocess2-setunmanagedbreakpoint-method.md).</span><span class="sxs-lookup"><span data-stu-id="5da5a-108">The specified breakpoint would have been previously set by an earlier call to [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md).</span></span>  
  
 <span data-ttu-id="5da5a-109">`ClearUnmanagedBreakpoint`Метод может быть вызван во время выполнения отлаживаемого процесса.</span><span class="sxs-lookup"><span data-stu-id="5da5a-109">The `ClearUnmanagedBreakpoint` method can be called while the process being debugged is running.</span></span>  
  
 <span data-ttu-id="5da5a-110">`ClearUnmanagedBreakpoint`Метод возвращает код ошибки, если отладчик присоединен в режиме «только управляемый» или если в указанном адресе не существует точки останова.</span><span class="sxs-lookup"><span data-stu-id="5da5a-110">The `ClearUnmanagedBreakpoint` method returns a failure code if the debugger is attached in managed-only mode or if no breakpoint exists at the specified address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5da5a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="5da5a-111">Requirements</span></span>  
 <span data-ttu-id="5da5a-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5da5a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da5a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5da5a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5da5a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5da5a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5da5a-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da5a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
