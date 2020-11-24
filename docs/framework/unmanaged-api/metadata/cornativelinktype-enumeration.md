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
ms.openlocfilehash: c155373f7da47e904c94a44efa2fba42309d4218
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671360"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="ce8bf-102">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="ce8bf-102">CorNativeLinkType Enumeration</span></span>

<span data-ttu-id="ce8bf-103">Предоставляет значения, указывающие тип, связанный в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce8bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce8bf-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="ce8bf-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ce8bf-105">Members</span></span>  
  
|<span data-ttu-id="ce8bf-106">Член</span><span class="sxs-lookup"><span data-stu-id="ce8bf-106">Member</span></span>|<span data-ttu-id="ce8bf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ce8bf-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="ce8bf-108">Указывает, что ни одно из ключевых слов не указано.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="ce8bf-109">Указывает, что указано ключевое слово ANSI.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="ce8bf-110">Указывает, что указано ключевое слово Юникода</span><span class="sxs-lookup"><span data-stu-id="ce8bf-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="ce8bf-111">Указывает, что указано ключевое слово auto.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="ce8bf-112">Указывает, что указано ключевое слово OLE.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="ce8bf-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="ce8bf-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce8bf-114">Требования</span><span class="sxs-lookup"><span data-stu-id="ce8bf-114">Requirements</span></span>  

 <span data-ttu-id="ce8bf-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce8bf-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce8bf-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ce8bf-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce8bf-117">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce8bf-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce8bf-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce8bf-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce8bf-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ce8bf-119">See also</span></span>

- [<span data-ttu-id="ce8bf-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ce8bf-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
