---
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: 41385fe915733f052af67c82d984c8b9d853c579
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713825"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="31476-102">Метод ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="31476-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>

<span data-ttu-id="31476-103">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="31476-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31476-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="31476-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31476-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="31476-105">Parameters</span></span>  

 `addr`  
 <span data-ttu-id="31476-106">Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее адрес в модуле.</span><span class="sxs-lookup"><span data-stu-id="31476-106">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="31476-107">заполняет Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="31476-107">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="31476-108">Указатель на размер модуля.</span><span class="sxs-lookup"><span data-stu-id="31476-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31476-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="31476-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="31476-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="31476-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31476-111">Требования</span><span class="sxs-lookup"><span data-stu-id="31476-111">Requirements</span></span>  

 <span data-ttu-id="31476-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31476-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31476-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31476-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31476-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31476-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31476-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31476-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31476-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="31476-116">See also</span></span>

- [<span data-ttu-id="31476-117">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="31476-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="31476-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="31476-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
