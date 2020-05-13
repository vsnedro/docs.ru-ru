---
title: Метод ICorDebugStaticFieldSymbol::GetSize
ms.date: 03/30/2017
ms.assetid: 72389860-7e37-4656-ba46-b6aeee1860f8
ms.openlocfilehash: e36c94bf411e75f915cca86aee74cdf161674d25
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379417"
---
# <a name="icordebugstaticfieldsymbolgetsize-method"></a><span data-ttu-id="5fcdc-102">Метод ICorDebugStaticFieldSymbol::GetSize</span><span class="sxs-lookup"><span data-stu-id="5fcdc-102">ICorDebugStaticFieldSymbol::GetSize Method</span></span>
<span data-ttu-id="5fcdc-103">Получает размер статического поля в байтах.</span><span class="sxs-lookup"><span data-stu-id="5fcdc-103">Gets the size in bytes of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fcdc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5fcdc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5fcdc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5fcdc-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="5fcdc-106">[out] Указатель на длину этого поля.</span><span class="sxs-lookup"><span data-stu-id="5fcdc-106">[out] A pointer to length of the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fcdc-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="5fcdc-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5fcdc-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="5fcdc-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fcdc-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5fcdc-109">Requirements</span></span>  
 <span data-ttu-id="5fcdc-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fcdc-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fcdc-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5fcdc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5fcdc-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fcdc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fcdc-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fcdc-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fcdc-114">См. также</span><span class="sxs-lookup"><span data-stu-id="5fcdc-114">See also</span></span>

- [<span data-ttu-id="5fcdc-115">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="5fcdc-115">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="5fcdc-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="5fcdc-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
