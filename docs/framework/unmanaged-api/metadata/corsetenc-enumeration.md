---
title: Перечисление CorSetENC
ms.date: 03/30/2017
api_name:
- CorSetENC
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetENC
helpviewer_keywords:
- CorSetENC enumeration [.NET Framework metadata]
ms.assetid: fe4150e8-071d-43fb-8e06-c3c616dbeed2
topic_type:
- apiref
ms.openlocfilehash: 93a194ea72ab894544927cf96304397b7211b5ac
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009162"
---
# <a name="corsetenc-enumeration"></a><span data-ttu-id="b6125-102">Перечисление CorSetENC</span><span class="sxs-lookup"><span data-stu-id="b6125-102">CorSetENC Enumeration</span></span>
<span data-ttu-id="b6125-103">Содержит значения, используемые для оказания влияния на поведение во время создания метаданных.</span><span class="sxs-lookup"><span data-stu-id="b6125-103">Contains values used to influence behavior during the generation of metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6125-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6125-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSetENC {  
  
    MDSetENCOn                  = 0x00000001,  
    MDSetENCOff                 = 0x00000002,  
  
    MDUpdateENC                 = 0x00000001,  
    MDUpdateFull                = 0x00000002,  
    MDUpdateExtension           = 0x00000003,  
    MDUpdateIncremental         = 0x00000004,  
    MDUpdateDelta               = 0x00000005,  
    MDUpdateMask                = 0x00000007  
  
} CorSetENC;  
```  
  
## <a name="members"></a><span data-ttu-id="b6125-105">Участники</span><span class="sxs-lookup"><span data-stu-id="b6125-105">Members</span></span>  
  
|<span data-ttu-id="b6125-106">Член</span><span class="sxs-lookup"><span data-stu-id="b6125-106">Member</span></span>|<span data-ttu-id="b6125-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b6125-107">Description</span></span>|  
|------------|-----------------|  
|`MDSetENCOn`|<span data-ttu-id="b6125-108">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="b6125-108">Obsolete.</span></span>|  
|`MDSetENCOff`|<span data-ttu-id="b6125-109">Устаревшее.</span><span class="sxs-lookup"><span data-stu-id="b6125-109">Obsolete.</span></span>|  
|`MDUpdateENC`|<span data-ttu-id="b6125-110">Указывает, что в то время как метаданные могут быть обновлены, токены перемещаться нельзя.</span><span class="sxs-lookup"><span data-stu-id="b6125-110">Indicates that whereas metadata can be updated, tokens cannot be moved.</span></span>|  
|`MDUpdateFull`|<span data-ttu-id="b6125-111">Указывает, что токены можно перемещать во время обновлений.</span><span class="sxs-lookup"><span data-stu-id="b6125-111">Indicates that tokens can be moved during updates.</span></span>|  
|`MDUpdateExtension`|<span data-ttu-id="b6125-112">Указывает, что обновления могут состоять только из добавлений.</span><span class="sxs-lookup"><span data-stu-id="b6125-112">Indicates that updates can consist only of additions.</span></span> <span data-ttu-id="b6125-113">Маркеры не могут быть перемещены.</span><span class="sxs-lookup"><span data-stu-id="b6125-113">Tokens cannot be moved.</span></span>|  
|`MDUpdateIncremental`|<span data-ttu-id="b6125-114">Указывает, что компиляция является добавочной.</span><span class="sxs-lookup"><span data-stu-id="b6125-114">Indicates that compilation is incremental.</span></span>|  
|`MDUpdateDelta`|<span data-ttu-id="b6125-115">Указывает, что должны быть сохранены только измененные метаданные.</span><span class="sxs-lookup"><span data-stu-id="b6125-115">Indicates that only changed metadata should be saved.</span></span>|  
|`MDUpdateMask`|<span data-ttu-id="b6125-116">Включает `MDUpdateENC` , `MDUpdateFull` и `MDUpdateIncremental` .</span><span class="sxs-lookup"><span data-stu-id="b6125-116">Includes `MDUpdateENC`, `MDUpdateFull` and `MDUpdateIncremental`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6125-117">Требования</span><span class="sxs-lookup"><span data-stu-id="b6125-117">Requirements</span></span>  
 <span data-ttu-id="b6125-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6125-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6125-119">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="b6125-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b6125-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6125-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6125-121">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b6125-121">See also</span></span>

- [<span data-ttu-id="b6125-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="b6125-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
