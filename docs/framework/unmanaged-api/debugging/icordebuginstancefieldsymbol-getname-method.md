---
title: Метод ICorDebugInstanceFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: e466a62761cc6dd1f1fc0a54f05d54f85c190d07
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724940"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="15ac2-102">Метод ICorDebugInstanceFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="15ac2-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>

<span data-ttu-id="15ac2-103">Получает имя поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="15ac2-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15ac2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15ac2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="15ac2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15ac2-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="15ac2-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="15ac2-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="15ac2-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="15ac2-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="15ac2-108">[out] Массив символов, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="15ac2-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15ac2-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="15ac2-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15ac2-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="15ac2-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15ac2-111">Требования</span><span class="sxs-lookup"><span data-stu-id="15ac2-111">Requirements</span></span>  

 <span data-ttu-id="15ac2-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15ac2-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15ac2-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="15ac2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="15ac2-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15ac2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15ac2-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15ac2-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15ac2-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="15ac2-116">See also</span></span>

- [<span data-ttu-id="15ac2-117">Интерфейс ICorDebugInstanceFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="15ac2-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="15ac2-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="15ac2-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
