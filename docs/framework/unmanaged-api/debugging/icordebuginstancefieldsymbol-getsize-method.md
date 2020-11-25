---
title: Метод ICorDebugInstanceFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: a4af1e3b-6a9f-4855-95ba-5317565c8e2b
ms.openlocfilehash: c4b193b45e30b0eba3367f18cb1e4c2b4e108fa8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724914"
---
# <a name="icordebuginstancefieldsymbolgetsize-method"></a><span data-ttu-id="096f8-102">Метод ICorDebugInstanceFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="096f8-102">ICorDebugInstanceFieldSymbol::GetSize Method</span></span>

<span data-ttu-id="096f8-103">Получает размер поля экземпляра в байтах.</span><span class="sxs-lookup"><span data-stu-id="096f8-103">Gets the size in bytes of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="096f8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="096f8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="096f8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="096f8-105">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="096f8-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="096f8-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="096f8-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="096f8-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="096f8-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="096f8-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="096f8-109">Требования</span><span class="sxs-lookup"><span data-stu-id="096f8-109">Requirements</span></span>  

 <span data-ttu-id="096f8-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="096f8-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="096f8-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="096f8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="096f8-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="096f8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="096f8-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="096f8-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096f8-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="096f8-114">See also</span></span>

- [<span data-ttu-id="096f8-115">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="096f8-115">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="096f8-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="096f8-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
