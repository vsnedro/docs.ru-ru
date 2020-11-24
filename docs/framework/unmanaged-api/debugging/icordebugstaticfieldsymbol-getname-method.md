---
title: Метод ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 6284a27921e0ba5bd3cedf07ef9f62348460ad06
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677240"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="0615a-102">Метод ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="0615a-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>

<span data-ttu-id="0615a-103">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="0615a-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0615a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0615a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0615a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0615a-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="0615a-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="0615a-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0615a-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="0615a-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="0615a-108">[out] Массив символов, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="0615a-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0615a-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0615a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0615a-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0615a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0615a-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0615a-111">Requirements</span></span>  

 <span data-ttu-id="0615a-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0615a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0615a-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0615a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0615a-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0615a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0615a-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0615a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0615a-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0615a-116">See also</span></span>

- [<span data-ttu-id="0615a-117">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="0615a-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="0615a-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0615a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
