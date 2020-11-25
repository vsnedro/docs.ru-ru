---
title: Метод ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 4937ff1be7736f98be9efb9b01bdb322bf33e037
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730812"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="00645-102">Метод ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="00645-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>

<span data-ttu-id="00645-103">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="00645-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00645-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00645-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00645-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00645-105">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="00645-106">[in] Число байтов в сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="00645-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="00645-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="00645-107">typeSig</span></span>  
 <span data-ttu-id="00645-108">[в] Сигнатура TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="00645-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="00645-109">[out] Указатель на размер объекта.</span><span class="sxs-lookup"><span data-stu-id="00645-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00645-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="00645-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="00645-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="00645-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00645-112">Требования</span><span class="sxs-lookup"><span data-stu-id="00645-112">Requirements</span></span>  

 <span data-ttu-id="00645-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00645-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00645-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00645-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00645-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00645-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00645-116">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00645-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00645-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="00645-117">See also</span></span>

- [<span data-ttu-id="00645-118">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="00645-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="00645-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="00645-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
