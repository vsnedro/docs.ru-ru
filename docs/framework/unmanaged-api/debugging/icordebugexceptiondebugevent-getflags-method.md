---
title: Метод ICorDebugExceptionDebugEvent::GetFlags
ms.date: 03/30/2017
ms.assetid: 73225303-8852-487e-9a0e-9f0cb95e99d9
ms.openlocfilehash: 02a20b54b7fecc711bda010c6916fe036cf20dd9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729607"
---
# <a name="icordebugexceptiondebugeventgetflags-method"></a><span data-ttu-id="c46d0-102">Метод ICorDebugExceptionDebugEvent::GetFlags</span><span class="sxs-lookup"><span data-stu-id="c46d0-102">ICorDebugExceptionDebugEvent::GetFlags Method</span></span>

<span data-ttu-id="c46d0-103">Возвращает флаг, указывающий, может ли исключение быть перехвачено.</span><span class="sxs-lookup"><span data-stu-id="c46d0-103">Gets a flag that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c46d0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c46d0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFlags(  
   [out] CorDebugExceptionFlags *pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c46d0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c46d0-105">Parameters</span></span>  

 `pdwFlags`  
 <span data-ttu-id="c46d0-106">заполняет Указатель на значение [кордебужексцептионфлагс](cordebugexceptionflags-enumeration.md) , указывающее, может ли быть перехвачено исключение.</span><span class="sxs-lookup"><span data-stu-id="c46d0-106">[out] A pointer to a [CorDebugExceptionFlags](cordebugexceptionflags-enumeration.md) value that indicates whether the exception can be intercepted.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c46d0-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c46d0-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c46d0-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="c46d0-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c46d0-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c46d0-109">Requirements</span></span>  

 <span data-ttu-id="c46d0-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c46d0-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c46d0-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c46d0-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c46d0-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c46d0-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c46d0-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c46d0-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c46d0-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c46d0-114">See also</span></span>

- [<span data-ttu-id="c46d0-115">Интерфейс ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c46d0-115">ICorDebugExceptionDebugEvent Interface</span></span>](icordebugexceptiondebugevent-interface.md)
- [<span data-ttu-id="c46d0-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="c46d0-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
