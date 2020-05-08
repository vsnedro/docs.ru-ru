---
title: Метод ICorDebugDataTarget2::GetImageFromPointer
ms.date: 03/30/2017
ms.assetid: 939cabe1-b647-4090-b662-eeec23c6c58d
ms.openlocfilehash: f316ddb04cdaad2f528e8fac0a970ca6263ebd8f
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976477"
---
# <a name="icordebugdatatarget2getimagefrompointer-method"></a><span data-ttu-id="6de26-102">Метод ICorDebugDataTarget2::GetImageFromPointer</span><span class="sxs-lookup"><span data-stu-id="6de26-102">ICorDebugDataTarget2::GetImageFromPointer Method</span></span>
<span data-ttu-id="6de26-103">Возвращает базовый адрес и размер модуля из адреса в этом модуле.</span><span class="sxs-lookup"><span data-stu-id="6de26-103">Returns the module base address and size from an address in that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de26-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6de26-104">Syntax</span></span>  
  
```cpp  
HRESULT GetImageFromPointer(  
   [in] CORDB_ADDRESS addr,
   [out] CORDB_ADDRESS *pImageBase,
   [out] ULONG32 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de26-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6de26-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="6de26-106">Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее адрес в модуле.</span><span class="sxs-lookup"><span data-stu-id="6de26-106">A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents an address in a module.</span></span>  
  
 `pImageBase`  
 <span data-ttu-id="6de26-107">заполняет Значение [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) , представляющее базовый адрес модуля.</span><span class="sxs-lookup"><span data-stu-id="6de26-107">[out] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `pSize`  
 <span data-ttu-id="6de26-108">Указатель на размер модуля.</span><span class="sxs-lookup"><span data-stu-id="6de26-108">A pointer to the module size.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6de26-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6de26-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6de26-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6de26-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de26-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6de26-111">Requirements</span></span>  
 <span data-ttu-id="6de26-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6de26-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de26-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6de26-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6de26-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6de26-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6de26-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de26-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de26-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6de26-116">See also</span></span>

- [<span data-ttu-id="6de26-117">Интерфейс ICorDebugDataTarget2</span><span class="sxs-lookup"><span data-stu-id="6de26-117">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="6de26-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6de26-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
