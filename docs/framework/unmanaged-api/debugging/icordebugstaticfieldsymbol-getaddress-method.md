---
title: Метод ICorDebugStaticFieldSymbol::GetAddress
ms.date: 03/30/2017
ms.assetid: 5a6c9a5a-ec72-4c40-a9c3-cee7baa63687
ms.openlocfilehash: 7b8072234df172eeafd77db90287ea3319c08ec7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378763"
---
# <a name="icordebugstaticfieldsymbolgetaddress-method"></a><span data-ttu-id="3cd3b-102">Метод ICorDebugStaticFieldSymbol::GetAddress</span><span class="sxs-lookup"><span data-stu-id="3cd3b-102">ICorDebugStaticFieldSymbol::GetAddress Method</span></span>
<span data-ttu-id="3cd3b-103">Получает адрес статического поля.</span><span class="sxs-lookup"><span data-stu-id="3cd3b-103">Gets the address of a static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cd3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3cd3b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress(  
   [out] CORDB_ADDRESS *pRVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3cd3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3cd3b-105">Parameters</span></span>  
 <span data-ttu-id="3cd3b-106">pRVA</span><span class="sxs-lookup"><span data-stu-id="3cd3b-106">pRVA</span></span>  
 <span data-ttu-id="3cd3b-107">[out] Указатель на относительный виртуальный адрес (RVA) статического поля.</span><span class="sxs-lookup"><span data-stu-id="3cd3b-107">[out] A pointer to the relative virtual address (RVA) of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3cd3b-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="3cd3b-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3cd3b-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="3cd3b-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cd3b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="3cd3b-110">Requirements</span></span>  
 <span data-ttu-id="3cd3b-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3cd3b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3cd3b-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3cd3b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3cd3b-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3cd3b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3cd3b-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3cd3b-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cd3b-115">См. также</span><span class="sxs-lookup"><span data-stu-id="3cd3b-115">See also</span></span>

- [<span data-ttu-id="3cd3b-116">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="3cd3b-116">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="3cd3b-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="3cd3b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
