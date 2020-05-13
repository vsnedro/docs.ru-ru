---
title: Метод ICorDebugLoadedModule::GetName
ms.date: 03/30/2017
ms.assetid: 88c304d5-edaa-4c0e-a8e1-144e8a76877e
ms.openlocfilehash: 4a0c4e99f23dc949b0bbaa8bbda35cff1537cf3c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209868"
---
# <a name="icordebugloadedmodulegetname-method"></a><span data-ttu-id="6f757-102">Метод ICorDebugLoadedModule::GetName</span><span class="sxs-lookup"><span data-stu-id="6f757-102">ICorDebugLoadedModule::GetName Method</span></span>
<span data-ttu-id="6f757-103">Получает имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="6f757-103">Gets the name of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f757-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f757-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,  
   [out] ULONG32 *pcchName,  
   [out, size_is(cchName),  
   length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f757-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f757-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="6f757-106">[in] Число символов в буфере `szName`.</span><span class="sxs-lookup"><span data-stu-id="6f757-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="6f757-107">[out] Указатель на число символов, фактически записанных в буфер `szName`.</span><span class="sxs-lookup"><span data-stu-id="6f757-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="6f757-108">[out] Массив символов, содержащий имя загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="6f757-108">[out] An array of characters that contain the name of the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f757-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="6f757-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f757-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6f757-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f757-111">Требования</span><span class="sxs-lookup"><span data-stu-id="6f757-111">Requirements</span></span>  
 <span data-ttu-id="6f757-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f757-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f757-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f757-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f757-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f757-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f757-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f757-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f757-116">См. также</span><span class="sxs-lookup"><span data-stu-id="6f757-116">See also</span></span>

- [<span data-ttu-id="6f757-117">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="6f757-117">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="6f757-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6f757-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
