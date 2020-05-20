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
ms.openlocfilehash: 5c3d1d0ebc56ee93c950afb4f015c8e10ec6a0f7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616181"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="43ed0-102">Перечисление ESymbolReadingPolicy</span><span class="sxs-lookup"><span data-stu-id="43ed0-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="43ed0-103">Содержит значения, задают политику чтения PDB-файлов.</span><span class="sxs-lookup"><span data-stu-id="43ed0-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ed0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="43ed0-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="43ed0-105">Участники</span><span class="sxs-lookup"><span data-stu-id="43ed0-105">Members</span></span>  
  
|<span data-ttu-id="43ed0-106">Член</span><span class="sxs-lookup"><span data-stu-id="43ed0-106">Member</span></span>|<span data-ttu-id="43ed0-107">Описание</span><span class="sxs-lookup"><span data-stu-id="43ed0-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="43ed0-108">Указывает, что отладчик всегда должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="43ed0-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="43ed0-109">Указывает, что отладчик должен считывать только PDB-файлы, связанные со сборками с полным доверием.</span><span class="sxs-lookup"><span data-stu-id="43ed0-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="43ed0-110">Указывает, что отладчик никогда не должен считывать PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="43ed0-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43ed0-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="43ed0-111">Remarks</span></span>  
 <span data-ttu-id="43ed0-112">`ESymbolReadingPolicy`Перечисление используется с методом [ICLRDebugManager:: SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="43ed0-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43ed0-113">Требования</span><span class="sxs-lookup"><span data-stu-id="43ed0-113">Requirements</span></span>  
 <span data-ttu-id="43ed0-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43ed0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43ed0-115">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="43ed0-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="43ed0-116">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="43ed0-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43ed0-117">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43ed0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ed0-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="43ed0-118">See also</span></span>

- [<span data-ttu-id="43ed0-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="43ed0-119">Hosting Enumerations</span></span>](hosting-enumerations.md)
