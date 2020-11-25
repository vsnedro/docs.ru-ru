---
title: Метод ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: c18af45184f5a9485e13b9d4789bff2c570834cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731856"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="0b30d-102">Метод ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="0b30d-102">ICorDebugLoadedModule::GetName Method</span></span>

<span data-ttu-id="0b30d-103">Получает имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="0b30d-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b30d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0b30d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b30d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0b30d-105">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="0b30d-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="0b30d-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="0b30d-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="0b30d-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="0b30d-108">[out] Массив символов, содержащий имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="0b30d-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0b30d-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="0b30d-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0b30d-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="0b30d-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b30d-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0b30d-111">Requirements</span></span>  

 <span data-ttu-id="0b30d-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b30d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b30d-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0b30d-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b30d-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b30d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b30d-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b30d-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b30d-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0b30d-116">See also</span></span>

- [<span data-ttu-id="0b30d-117">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="0b30d-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="0b30d-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0b30d-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
