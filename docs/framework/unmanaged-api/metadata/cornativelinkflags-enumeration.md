---
title: Перечисление CorNativeLinkFlags
ms.date: 03/30/2017
api_name:
- CorNativeLinkFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkFlags
helpviewer_keywords:
- CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type:
- apiref
ms.openlocfilehash: ef9b177bee0651b6b8ea994610315ce93524e8e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676937"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="18f52-102">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="18f52-102">CorNativeLinkFlags Enumeration</span></span>

<span data-ttu-id="18f52-103">Предоставляет значения флагов, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="18f52-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18f52-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18f52-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="18f52-105">Члены</span><span class="sxs-lookup"><span data-stu-id="18f52-105">Members</span></span>  
  
|<span data-ttu-id="18f52-106">Член</span><span class="sxs-lookup"><span data-stu-id="18f52-106">Member</span></span>|<span data-ttu-id="18f52-107">Описание</span><span class="sxs-lookup"><span data-stu-id="18f52-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="18f52-108">Указывает, что флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="18f52-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="18f52-109">Указывает `setLastError` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="18f52-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="18f52-110">Указывает `nomangle` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="18f52-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="18f52-111">Не используется.</span><span class="sxs-lookup"><span data-stu-id="18f52-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="18f52-112">Требования</span><span class="sxs-lookup"><span data-stu-id="18f52-112">Requirements</span></span>  

 <span data-ttu-id="18f52-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18f52-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18f52-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="18f52-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18f52-115">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="18f52-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18f52-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18f52-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f52-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="18f52-117">See also</span></span>

- [<span data-ttu-id="18f52-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="18f52-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
