---
title: Метод ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 5793d939c8497ef842f614048707f69faa8ac568
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976048"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="8d1f6-102">Метод ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="8d1f6-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>
<span data-ttu-id="8d1f6-103">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="8d1f6-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d1f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d1f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d1f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8d1f6-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="8d1f6-106">заполняет Указатель на значение [кордебужексцептионфлагс](cordebugexceptionflags-enumeration.md) , указывающее, может ли быть перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="8d1f6-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d1f6-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="8d1f6-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d1f6-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="8d1f6-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d1f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8d1f6-109">Requirements</span></span>  
 <span data-ttu-id="8d1f6-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d1f6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d1f6-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d1f6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d1f6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d1f6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d1f6-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d1f6-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d1f6-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8d1f6-114">See also</span></span>

- [<span data-ttu-id="8d1f6-115">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="8d1f6-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="8d1f6-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8d1f6-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
