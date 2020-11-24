---
title: Перечисление CorLinkerOptions
ms.date: 03/30/2017
api_name:
- CorLinkerOptions
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLinkerOptions
helpviewer_keywords:
- CorLinkerOptions enumeration [.NET Framework metadata]
ms.assetid: a656aad6-cc7e-4994-8251-004a6a45e18f
topic_type:
- apiref
ms.openlocfilehash: 188301d31b2fcfaf7b1c6139111e8f1296ccf7e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677249"
---
# <a name="corlinkeroptions-enumeration"></a><span data-ttu-id="bfaba-102">Перечисление CorLinkerOptions</span><span class="sxs-lookup"><span data-stu-id="bfaba-102">CorLinkerOptions Enumeration</span></span>

<span data-ttu-id="bfaba-103">Задает флаги для выбора параметров компоновщика метаданных.</span><span class="sxs-lookup"><span data-stu-id="bfaba-103">Specifies flags to select options for the metadata linker.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfaba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bfaba-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLinkerOptions {  
    MDAssembly          = 0x00000000,  
    MDNetModule         = 0x00000001,  
} CorLinkerOptions;  
```  
  
## <a name="members"></a><span data-ttu-id="bfaba-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bfaba-105">Members</span></span>  
  
|<span data-ttu-id="bfaba-106">Член</span><span class="sxs-lookup"><span data-stu-id="bfaba-106">Member</span></span>|<span data-ttu-id="bfaba-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bfaba-107">Description</span></span>|  
|------------|-----------------|  
|`MDAssembly`|<span data-ttu-id="bfaba-108">Закрытые типы и глобальные функции не сохраняются.</span><span class="sxs-lookup"><span data-stu-id="bfaba-108">The private types and global functions are not preserved.</span></span>|  
|`MDNetModule`|<span data-ttu-id="bfaba-109">Закрытые типы и глобальные функции сохраняются.</span><span class="sxs-lookup"><span data-stu-id="bfaba-109">The private types and global functions are preserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfaba-110">Требования</span><span class="sxs-lookup"><span data-stu-id="bfaba-110">Requirements</span></span>  

 <span data-ttu-id="bfaba-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfaba-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfaba-112">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="bfaba-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bfaba-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfaba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfaba-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bfaba-114">See also</span></span>

- [<span data-ttu-id="bfaba-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="bfaba-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
