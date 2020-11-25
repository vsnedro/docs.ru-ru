---
title: Перечисление ESymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 42ce1f02294db98c5c593a5f16de5226703d5f9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733715"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="e8b6d-102">Перечисление ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="e8b6d-102">ESymbolReadingPolicy Enumeration</span></span>

<span data-ttu-id="e8b6d-103">Содержит значения, задают политику чтения PDB-файлов.</span><span class="sxs-lookup"><span data-stu-id="e8b6d-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8b6d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8b6d-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="e8b6d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e8b6d-105">Members</span></span>  
  
|<span data-ttu-id="e8b6d-106">Член</span><span class="sxs-lookup"><span data-stu-id="e8b6d-106">Member</span></span>|<span data-ttu-id="e8b6d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e8b6d-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="e8b6d-108">Указывает, что отладчик всегда должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="e8b6d-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="e8b6d-109">Указывает, что отладчик должен считывать только PDB-файлы, связанные со сборками с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="e8b6d-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="e8b6d-110">Указывает, что отладчик никогда не должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="e8b6d-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8b6d-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e8b6d-111">Remarks</span></span>  

 <span data-ttu-id="e8b6d-112">`ESymbolReadingPolicy`Перечисление используется с методом [ICLRDebugManager:: SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e8b6d-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8b6d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e8b6d-113">Requirements</span></span>  

 <span data-ttu-id="e8b6d-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8b6d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8b6d-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="e8b6d-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e8b6d-116">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8b6d-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8b6d-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8b6d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8b6d-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e8b6d-118">See also</span></span>

- [<span data-ttu-id="e8b6d-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="e8b6d-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
