---
title: Метод ICorDebugVariableSymbol::GetName
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: ea414a39e140c74df736764dbbb1bb3934bda78f
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397132"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="6bcd6-102">Метод ICorDebugVariableSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="6bcd6-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="6bcd6-103">Получает имя переменной.</span><span class="sxs-lookup"><span data-stu-id="6bcd6-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bcd6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6bcd6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bcd6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6bcd6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6bcd6-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="6bcd6-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6bcd6-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="6bcd6-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="6bcd6-108">Указатель на массив символов, содержащий имя переменной.</span><span class="sxs-lookup"><span data-stu-id="6bcd6-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6bcd6-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6bcd6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6bcd6-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6bcd6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6bcd6-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6bcd6-111">Requirements</span></span>  
 <span data-ttu-id="6bcd6-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bcd6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bcd6-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6bcd6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6bcd6-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6bcd6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6bcd6-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bcd6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bcd6-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6bcd6-116">See also</span></span>

- [<span data-ttu-id="6bcd6-117">Интерфейс ICorDebugVariableSymbol</span><span class="sxs-lookup"><span data-stu-id="6bcd6-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="6bcd6-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6bcd6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
