---
title: Метод ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: fc42517cb95dfc14c472b5bb9111ebd70639cee7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725993"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="54900-102">Метод ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="54900-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>

<span data-ttu-id="54900-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="54900-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54900-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="54900-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54900-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="54900-105">Parameters</span></span>  

 `pSlotIndex`  
 <span data-ttu-id="54900-106">[выходной] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="54900-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="54900-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="54900-107">Return Value</span></span>  

 <span data-ttu-id="54900-108">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="54900-108">`S_OK` if successful.</span></span> <span data-ttu-id="54900-109">`E_FAIL`, если переменная является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="54900-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54900-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="54900-110">Remarks</span></span>  

 <span data-ttu-id="54900-111">Управляемый индекс слота можно использовать для получения информации о метаданных переменной.</span><span class="sxs-lookup"><span data-stu-id="54900-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54900-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="54900-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54900-113">Требования</span><span class="sxs-lookup"><span data-stu-id="54900-113">Requirements</span></span>  

 <span data-ttu-id="54900-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54900-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54900-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54900-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54900-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54900-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54900-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54900-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54900-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="54900-118">See also</span></span>

- [<span data-ttu-id="54900-119">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="54900-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="54900-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="54900-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
