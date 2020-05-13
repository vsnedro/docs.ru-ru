---
title: Метод ICorDebugSymbolProvider::GetObjectSize
ms.date: 03/30/2017
ms.assetid: 3c564396-ac64-4ef3-b4f6-df96f1d46fc7
ms.openlocfilehash: 64324df49ad0b5dfa3c25455950bddc3d687b178
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379561"
---
# <a name="icordebugsymbolprovidergetobjectsize-method"></a><span data-ttu-id="b47ec-102">Метод ICorDebugSymbolProvider::GetObjectSize</span><span class="sxs-lookup"><span data-stu-id="b47ec-102">ICorDebugSymbolProvider::GetObjectSize Method</span></span>
<span data-ttu-id="b47ec-103">Возвращает размер объекта для объекта на основе его сигнатуры TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="b47ec-103">Returns the object size for an object based on its typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b47ec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b47ec-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [out] ULONG32 *pObjectSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b47ec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b47ec-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="b47ec-106">[in] Число байтов в сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="b47ec-106">[in] The number of bytes in the typespec signature.</span></span>  
  
 <span data-ttu-id="b47ec-107">typeSig</span><span class="sxs-lookup"><span data-stu-id="b47ec-107">typeSig</span></span>  
 <span data-ttu-id="b47ec-108">[в] Сигнатура TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="b47ec-108">[in] The typespec signature.</span></span>  
  
 `pObjectSize`  
 <span data-ttu-id="b47ec-109">[out] Указатель на размер объекта.</span><span class="sxs-lookup"><span data-stu-id="b47ec-109">[out] A pointer to the size of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b47ec-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="b47ec-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b47ec-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="b47ec-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b47ec-112">Требования</span><span class="sxs-lookup"><span data-stu-id="b47ec-112">Requirements</span></span>  
 <span data-ttu-id="b47ec-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b47ec-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b47ec-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b47ec-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b47ec-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b47ec-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b47ec-116">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b47ec-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b47ec-117">См. также</span><span class="sxs-lookup"><span data-stu-id="b47ec-117">See also</span></span>

- [<span data-ttu-id="b47ec-118">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="b47ec-118">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="b47ec-119">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="b47ec-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
