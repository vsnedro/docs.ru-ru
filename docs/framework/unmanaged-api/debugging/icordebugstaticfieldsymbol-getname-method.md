---
title: Метод ICorDebugStaticFieldSymbol::GetName
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 75f5324296f9b42406157d06351f7e680a749444
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378753"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="67244-102">Метод ICorDebugStaticFieldSymbol::GetName</span><span class="sxs-lookup"><span data-stu-id="67244-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="67244-103">Получает имя статического поля.</span><span class="sxs-lookup"><span data-stu-id="67244-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67244-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67244-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67244-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="67244-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="67244-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="67244-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="67244-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="67244-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="67244-108">[out] Массив символов, в котором хранится возвращаемое имя.</span><span class="sxs-lookup"><span data-stu-id="67244-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67244-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="67244-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="67244-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="67244-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67244-111">Требования</span><span class="sxs-lookup"><span data-stu-id="67244-111">Requirements</span></span>  
 <span data-ttu-id="67244-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67244-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67244-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67244-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67244-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67244-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67244-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67244-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67244-116">См. также</span><span class="sxs-lookup"><span data-stu-id="67244-116">See also</span></span>

- [<span data-ttu-id="67244-117">Интерфейс ICorDebugStaticFieldSymbol</span><span class="sxs-lookup"><span data-stu-id="67244-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="67244-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="67244-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
