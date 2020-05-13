---
title: Метод ICorDebugMergedAssemblyRecord::GetIndex
ms.date: 03/30/2017
ms.assetid: 98701444-b9bc-4978-9548-89ac3394147d
ms.openlocfilehash: b13e589e32b3317b567a4a89a5b48fc1299a1a84
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206952"
---
# <a name="icordebugmergedassemblyrecordgetindex-method"></a><span data-ttu-id="6a1ee-102">Метод ICorDebugMergedAssemblyRecord::GetIndex</span><span class="sxs-lookup"><span data-stu-id="6a1ee-102">ICorDebugMergedAssemblyRecord::GetIndex Method</span></span>
<span data-ttu-id="6a1ee-103">Возвращает индекс префикса сборки.</span><span class="sxs-lookup"><span data-stu-id="6a1ee-103">Gets the assembly's prefix index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1ee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6a1ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIndex(  
   [out] ULONG32 *pIndex  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a1ee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6a1ee-105">Parameters</span></span>  
 `pIndex`  
 <span data-ttu-id="6a1ee-106">[out] Указатель на индекс префикса.</span><span class="sxs-lookup"><span data-stu-id="6a1ee-106">[out] A pointer to the prefix index.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6a1ee-107">Remarks</span><span class="sxs-lookup"><span data-stu-id="6a1ee-107">Remarks</span></span>  
 <span data-ttu-id="6a1ee-108">Индекс префикса используется для предотвращения конфликтов имен в типе объединенных метаданных.</span><span class="sxs-lookup"><span data-stu-id="6a1ee-108">The prefix index is used to prevent name collisions in the merged metadata type names.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a1ee-109">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="6a1ee-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a1ee-110">Требования</span><span class="sxs-lookup"><span data-stu-id="6a1ee-110">Requirements</span></span>  
 <span data-ttu-id="6a1ee-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a1ee-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a1ee-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6a1ee-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6a1ee-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a1ee-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a1ee-114">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a1ee-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a1ee-115">См. также</span><span class="sxs-lookup"><span data-stu-id="6a1ee-115">See also</span></span>

- [<span data-ttu-id="6a1ee-116">Интерфейс ICorDebugMergedAssemblyRecord</span><span class="sxs-lookup"><span data-stu-id="6a1ee-116">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="6a1ee-117">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6a1ee-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
