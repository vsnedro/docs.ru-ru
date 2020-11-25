---
title: Метод ICorDebugInstanceFieldSymbol::GetOffset
ms.date: 03/30/2017
ms.assetid: 7e470150-2b92-4425-989c-315f48964fd2
ms.openlocfilehash: 2d73de46bbb1023f20dd9023076630611c74be5d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724927"
---
# <a name="icordebuginstancefieldsymbolgetoffset-method"></a><span data-ttu-id="fd63d-102">Метод ICorDebugInstanceFieldSymbol::GetOffset</span><span class="sxs-lookup"><span data-stu-id="fd63d-102">ICorDebugInstanceFieldSymbol::GetOffset Method</span></span>

<span data-ttu-id="fd63d-103">Возвращает смещение в байтах этого поля экземпляра в его родительском классе.</span><span class="sxs-lookup"><span data-stu-id="fd63d-103">Gets the offset in bytes of this instance field in its parent class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd63d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fd63d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
   [out] ULONG32 *pcbOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd63d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fd63d-105">Parameters</span></span>  

 `pcbOffset`  
 <span data-ttu-id="fd63d-106">Указатель на число байтов, на которое это поле экземпляра смещается в своем родительском классе.</span><span class="sxs-lookup"><span data-stu-id="fd63d-106">A pointer to the number of bytes that this instance field is offset in its parent class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd63d-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="fd63d-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fd63d-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="fd63d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd63d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="fd63d-109">Requirements</span></span>  

 <span data-ttu-id="fd63d-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd63d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd63d-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd63d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd63d-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd63d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd63d-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd63d-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd63d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fd63d-114">See also</span></span>

- [<span data-ttu-id="fd63d-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="fd63d-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="fd63d-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="fd63d-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
