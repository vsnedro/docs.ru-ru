---
title: Метод ICorDebugLoadedModule::GetBaseAddress
ms.date: 03/30/2017
ms.assetid: 7c036772-d58a-47f1-a5fa-31779898ef0d
ms.openlocfilehash: d8c91c10577efd6a76af778cd01002de006df43a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209881"
---
# <a name="icordebugloadedmodulegetbaseaddress-method"></a><span data-ttu-id="779d4-102">Метод ICorDebugLoadedModule::GetBaseAddress</span><span class="sxs-lookup"><span data-stu-id="779d4-102">ICorDebugLoadedModule::GetBaseAddress Method</span></span>
<span data-ttu-id="779d4-103">Получает базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="779d4-103">Gets the base address of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="779d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="779d4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBaseAddress(  
   [out] CORDB_ADDRESS *pAddress  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="779d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="779d4-105">Parameters</span></span>  
 `pAddress`  
 <span data-ttu-id="779d4-106">[out] Указатель на базовый адрес загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="779d4-106">[out] A pointer to the base address of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="779d4-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="779d4-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="779d4-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="779d4-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="779d4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="779d4-109">Requirements</span></span>  
 <span data-ttu-id="779d4-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="779d4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="779d4-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="779d4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="779d4-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="779d4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="779d4-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="779d4-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="779d4-114">См. также</span><span class="sxs-lookup"><span data-stu-id="779d4-114">See also</span></span>

- [<span data-ttu-id="779d4-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="779d4-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="779d4-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="779d4-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
