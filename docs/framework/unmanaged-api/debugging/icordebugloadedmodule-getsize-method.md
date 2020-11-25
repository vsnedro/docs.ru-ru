---
title: Метод ICorDebugLoadedModule::GetSize
ms.date: 03/30/2017
ms.assetid: aaa0e5c0-be9d-4fe1-8418-5295b9b184d6
ms.openlocfilehash: 2ed19cb4a190f2af7581a827e8bd11b748b3d4a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721326"
---
# <a name="icordebugloadedmodulegetsize-method"></a><span data-ttu-id="515a2-102">Метод ICorDebugLoadedModule::GetSize</span><span class="sxs-lookup"><span data-stu-id="515a2-102">ICorDebugLoadedModule::GetSize Method</span></span>

<span data-ttu-id="515a2-103">Возвращает размер в байтах загруженного модуля.</span><span class="sxs-lookup"><span data-stu-id="515a2-103">Gets the size in bytes of the loaded module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="515a2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="515a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize(  
   [out] ULONG32 *pcBytes  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="515a2-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="515a2-105">Parameters</span></span>  

 `pcBytes`  
 <span data-ttu-id="515a2-106">[out] Указатель на число байтов в загруженном модуле.</span><span class="sxs-lookup"><span data-stu-id="515a2-106">[out] A pointer to the number of bytes in the loaded module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="515a2-107">Комментарии</span><span class="sxs-lookup"><span data-stu-id="515a2-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="515a2-108">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="515a2-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="515a2-109">Требования</span><span class="sxs-lookup"><span data-stu-id="515a2-109">Requirements</span></span>  

 <span data-ttu-id="515a2-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="515a2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="515a2-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="515a2-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="515a2-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="515a2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="515a2-113">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="515a2-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="515a2-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="515a2-114">See also</span></span>

- [<span data-ttu-id="515a2-115">Интерфейс ICorDebugLoadedModule</span><span class="sxs-lookup"><span data-stu-id="515a2-115">ICorDebugLoadedModule Interface</span></span>](icordebugloadedmodule-interface.md)
- [<span data-ttu-id="515a2-116">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="515a2-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
