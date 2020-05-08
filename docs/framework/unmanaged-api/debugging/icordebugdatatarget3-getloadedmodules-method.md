---
title: Метод ICorDebugDataTarget3::GetLoadedModules
ms.date: 03/30/2017
ms.assetid: 9a48c05b-1949-416e-933c-52549b6fcf5e
ms.openlocfilehash: c3565f4f9284bc121b0e2d3b0885cbea927acfdd
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976425"
---
# <a name="icordebugdatatarget3getloadedmodules-method"></a><span data-ttu-id="d56fe-102">Метод ICorDebugDataTarget3::GetLoadedModules</span><span class="sxs-lookup"><span data-stu-id="d56fe-102">ICorDebugDataTarget3::GetLoadedModules Method</span></span>
<span data-ttu-id="d56fe-103">Возвращает список модулей, загруженных на данный момент.</span><span class="sxs-lookup"><span data-stu-id="d56fe-103">Gets a list of the modules that have been loaded so far.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d56fe-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d56fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLoadedModules(  
   [in] ULONG32 cRequestedModules,  
   [out] ULONG32 *pcFetchedModules,  
   [out, size_is(cRequestedModules), length_is(*pcFetchedModules)] ICorDebugLoadedModule *pLoadedModules[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d56fe-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d56fe-105">Parameters</span></span>  
 `cRequestedModules`  
 <span data-ttu-id="d56fe-106">[in] Число модулей, для которых запрашиваются сведения.</span><span class="sxs-lookup"><span data-stu-id="d56fe-106">[in] The number of modules for which information is requested.</span></span>  
  
 `pcFetchedModules`  
 <span data-ttu-id="d56fe-107">[out] Указатель на число модулей, о которых возвращаются сведения.</span><span class="sxs-lookup"><span data-stu-id="d56fe-107">[out] A pointer to the number of modules about which information was returned.</span></span>  
  
 `pLoadedModules`  
 <span data-ttu-id="d56fe-108">заполняет Указатель на массив объектов [икордебуглоадедмодуле](icordebugloadedmodule-interface.md) , которые предоставляют сведения о загруженных модулях.</span><span class="sxs-lookup"><span data-stu-id="d56fe-108">[out] A pointer to an array of [ICorDebugLoadedModule](icordebugloadedmodule-interface.md) objects that provide information about loaded modules.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d56fe-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="d56fe-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d56fe-110">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="d56fe-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d56fe-111">Требования</span><span class="sxs-lookup"><span data-stu-id="d56fe-111">Requirements</span></span>  
 <span data-ttu-id="d56fe-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d56fe-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d56fe-113">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d56fe-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d56fe-114">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d56fe-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d56fe-115">**.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d56fe-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d56fe-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d56fe-116">See also</span></span>

- [<span data-ttu-id="d56fe-117">Интерфейс ICorDebugDataTarget3</span><span class="sxs-lookup"><span data-stu-id="d56fe-117">ICorDebugDataTarget3 Interface</span></span>](icordebugdatatarget3-interface.md)
- [<span data-ttu-id="d56fe-118">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d56fe-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
