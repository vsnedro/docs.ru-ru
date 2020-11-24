---
title: Функция CreateAssemblyCache
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
ms.openlocfilehash: 3197c650b4f167e7a5043270797d2c4a62413d8e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95683203"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="e63ab-102">Функция CreateAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="e63ab-102">CreateAssemblyCache Function</span></span>

<span data-ttu-id="e63ab-103">Возвращает указатель на новый экземпляр [IAssemblyCache](iassemblycache-interface.md) , представляющий глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="e63ab-103">Gets a pointer to a new [IAssemblyCache](iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e63ab-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e63ab-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e63ab-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e63ab-105">Parameters</span></span>  

 `ppAsmCache`  
 <span data-ttu-id="e63ab-106">заполняет Возвращаемый `IAssemblyCache` указатель.</span><span class="sxs-lookup"><span data-stu-id="e63ab-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="e63ab-107">окне Зарезервировано для будущего расширения.</span><span class="sxs-lookup"><span data-stu-id="e63ab-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e63ab-108">`dwReserved` значение должно быть равно 0 (нулю).</span><span class="sxs-lookup"><span data-stu-id="e63ab-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e63ab-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e63ab-109">Requirements</span></span>  

 <span data-ttu-id="e63ab-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e63ab-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e63ab-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e63ab-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e63ab-112">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e63ab-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e63ab-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e63ab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e63ab-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e63ab-114">See also</span></span>

- [<span data-ttu-id="e63ab-115">Интерфейс IAssemblyCache</span><span class="sxs-lookup"><span data-stu-id="e63ab-115">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="e63ab-116">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="e63ab-116">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
- [<span data-ttu-id="e63ab-117">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="e63ab-117">Global Assembly Cache</span></span>](../../app-domains/gac.md)
