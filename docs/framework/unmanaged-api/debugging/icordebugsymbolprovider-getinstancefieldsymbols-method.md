---
title: Метод ICorDebugSymbolProvider::GetInstanceFieldSymbols
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 9ecc61ed6cac73a519f33e00cbfbfecc20ac2ebe
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379632"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="2efe8-102">Метод ICorDebugSymbolProvider::GetInstanceFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="2efe8-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="2efe8-103">Получает символы поля экземпляра, которые соответствуют сигнатуре TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="2efe8-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2efe8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2efe8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2efe8-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2efe8-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="2efe8-106">[in] Число байтов в массиве `typeSig`.</span><span class="sxs-lookup"><span data-stu-id="2efe8-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="2efe8-107">[in] Массив байтов, содержащий сигнатуру `typespec`.</span><span class="sxs-lookup"><span data-stu-id="2efe8-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="2efe8-108">[in] Количество запрошенных символов.</span><span class="sxs-lookup"><span data-stu-id="2efe8-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="2efe8-109">[out] Указатель на число  символов, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="2efe8-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="2efe8-110">заполняет Указатель на массив [икордебугстатикфиелдсимбол](icordebugstaticfieldsymbol-interface.md) , содержащий запрошенные символы поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="2efe8-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2efe8-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="2efe8-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2efe8-112">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="2efe8-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2efe8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="2efe8-113">Requirements</span></span>  
 <span data-ttu-id="2efe8-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2efe8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2efe8-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2efe8-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2efe8-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2efe8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2efe8-117">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2efe8-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2efe8-118">См. также</span><span class="sxs-lookup"><span data-stu-id="2efe8-118">See also</span></span>

- [<span data-ttu-id="2efe8-119">Метод GetStaticFieldSymbols</span><span class="sxs-lookup"><span data-stu-id="2efe8-119">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="2efe8-120">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="2efe8-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="2efe8-121">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="2efe8-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
