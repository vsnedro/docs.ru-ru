---
title: Метод ICorDebugVariableSymbol::GetSlotIndex
ms.date: 03/30/2017
ms.assetid: 09c19f5f-afc4-4e0c-bffe-cd7147bc7a43
ms.openlocfilehash: 251a978e96ff396d0d9d9282ded7f8a25ae0ba0b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397084"
---
# <a name="icordebugvariablesymbolgetslotindex-method"></a><span data-ttu-id="08426-102">Метод ICorDebugVariableSymbol::GetSlotIndex</span><span class="sxs-lookup"><span data-stu-id="08426-102">ICorDebugVariableSymbol::GetSlotIndex Method</span></span>
<span data-ttu-id="08426-103">Возвращает управляемый индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="08426-103">Gets the managed slot index of a local variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08426-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08426-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSlotIndex(  
   [out] ULONG32 *pSlotIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08426-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="08426-105">Parameters</span></span>  
 `pSlotIndex`  
 <span data-ttu-id="08426-106">[выходной] Указатель на индекс слота локальной переменной.</span><span class="sxs-lookup"><span data-stu-id="08426-106">[out] A pointer to the local variable's slot index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08426-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="08426-107">Return Value</span></span>  
 <span data-ttu-id="08426-108">`S_OK` в случае успешного выполнения.</span><span class="sxs-lookup"><span data-stu-id="08426-108">`S_OK` if successful.</span></span> <span data-ttu-id="08426-109">`E_FAIL`, если переменная является аргументом функции.</span><span class="sxs-lookup"><span data-stu-id="08426-109">`E_FAIL` if the variable is a function argument.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08426-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="08426-110">Remarks</span></span>  
 <span data-ttu-id="08426-111">Управляемый индекс слота можно использовать для получения информации о метаданных переменной.</span><span class="sxs-lookup"><span data-stu-id="08426-111">The managed slot index of a local variable can be used to retrieve the variable's metadata information</span></span>  
  
> [!NOTE]
> <span data-ttu-id="08426-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="08426-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08426-113">Требования</span><span class="sxs-lookup"><span data-stu-id="08426-113">Requirements</span></span>  
 <span data-ttu-id="08426-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08426-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08426-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08426-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08426-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08426-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08426-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08426-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08426-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="08426-118">See also</span></span>

- [<span data-ttu-id="08426-119">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="08426-119">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="08426-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="08426-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
