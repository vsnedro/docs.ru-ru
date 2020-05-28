---
title: Перечисление CorNativeLinkType
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
ms.openlocfilehash: 29f2401e2e3faccae05ca5249fcd7d9e89aacb46
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007615"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="6281e-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="6281e-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="6281e-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="6281e-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6281e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6281e-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="6281e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6281e-105">Members</span></span>  
  
|<span data-ttu-id="6281e-106">Член</span><span class="sxs-lookup"><span data-stu-id="6281e-106">Member</span></span>|<span data-ttu-id="6281e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6281e-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="6281e-108">Указывает, что ни одно из ключевых слов не указано.</span><span class="sxs-lookup"><span data-stu-id="6281e-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="6281e-109">Указывает, что указано ключевое слово ANSI.</span><span class="sxs-lookup"><span data-stu-id="6281e-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="6281e-110">Указывает, что указано ключевое слово Юникода</span><span class="sxs-lookup"><span data-stu-id="6281e-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="6281e-111">Указывает, что указано ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="6281e-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="6281e-112">Указывает, что указано ключевое слово OLE.</span><span class="sxs-lookup"><span data-stu-id="6281e-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="6281e-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="6281e-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6281e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="6281e-114">Requirements</span></span>  
 <span data-ttu-id="6281e-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6281e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6281e-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6281e-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6281e-117">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6281e-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6281e-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6281e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6281e-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="6281e-119">See also</span></span>

- [<span data-ttu-id="6281e-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="6281e-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
