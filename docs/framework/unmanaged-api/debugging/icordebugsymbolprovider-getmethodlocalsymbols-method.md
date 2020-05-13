---
title: Метод ICorDebugSymbolProvider::GetMethodLocalSymbols
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: 7e9aa01a3fa1c90b0ab4f85970c4eb294b9a4904
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379614"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="446da-102">Метод ICorDebugSymbolProvider::GetMethodLocalSymbols</span><span class="sxs-lookup"><span data-stu-id="446da-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>
<span data-ttu-id="446da-103">Получает локальные символы метода с учетом относительного виртуального адреса (RVA) этого метода.</span><span class="sxs-lookup"><span data-stu-id="446da-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="446da-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="446da-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="446da-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="446da-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="446da-106">[in] Собственный относительный виртуальный адрес метода.</span><span class="sxs-lookup"><span data-stu-id="446da-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="446da-107">[in] Количество запрошенных локальных символов.</span><span class="sxs-lookup"><span data-stu-id="446da-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="446da-108">[out] Указатель на число  символов, полученных при помощи метода.</span><span class="sxs-lookup"><span data-stu-id="446da-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="446da-109">заполняет Указатель на массив [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) , содержащий локальные символы метода.</span><span class="sxs-lookup"><span data-stu-id="446da-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="446da-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="446da-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="446da-111">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="446da-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="446da-112">Требования</span><span class="sxs-lookup"><span data-stu-id="446da-112">Requirements</span></span>  
 <span data-ttu-id="446da-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="446da-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="446da-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="446da-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="446da-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="446da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="446da-116">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="446da-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="446da-117">См. также</span><span class="sxs-lookup"><span data-stu-id="446da-117">See also</span></span>

- [<span data-ttu-id="446da-118">Метод GetMethodParameterSymbols</span><span class="sxs-lookup"><span data-stu-id="446da-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="446da-119">Интерфейс ICorDebugSymbolProvider</span><span class="sxs-lookup"><span data-stu-id="446da-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="446da-120">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="446da-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
