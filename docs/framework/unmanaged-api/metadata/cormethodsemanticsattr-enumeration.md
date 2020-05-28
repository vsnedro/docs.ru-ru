---
title: Перечисление CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 1572c206f4a5a5fe0fd189ca84d0bcda2249c6d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007654"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="e279a-102">Перечисление CorMethodSemanticsAttr</span><span class="sxs-lookup"><span data-stu-id="e279a-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="e279a-103">Содержит значения, описывающие связь между методом и соответствующим свойством или событием.</span><span class="sxs-lookup"><span data-stu-id="e279a-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e279a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e279a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="e279a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="e279a-105">Members</span></span>  
  
|<span data-ttu-id="e279a-106">Член</span><span class="sxs-lookup"><span data-stu-id="e279a-106">Member</span></span>|<span data-ttu-id="e279a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e279a-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="e279a-108">Указывает, что метод является методом `set` доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="e279a-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="e279a-109">Указывает, что метод является методом `get` доступа для свойства.</span><span class="sxs-lookup"><span data-stu-id="e279a-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="e279a-110">Указывает, что метод имеет связь со свойством или событием, отличным от указанных здесь.</span><span class="sxs-lookup"><span data-stu-id="e279a-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="e279a-111">Указывает, что метод добавляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="e279a-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="e279a-112">Указывает, что метод удаляет методы обработчика для события.</span><span class="sxs-lookup"><span data-stu-id="e279a-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="e279a-113">Указывает, что метод вызывает событие.</span><span class="sxs-lookup"><span data-stu-id="e279a-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e279a-114">Требования</span><span class="sxs-lookup"><span data-stu-id="e279a-114">Requirements</span></span>  
 <span data-ttu-id="e279a-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e279a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e279a-116">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="e279a-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e279a-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e279a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e279a-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="e279a-118">See also</span></span>

- [<span data-ttu-id="e279a-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="e279a-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
