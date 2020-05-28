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
ms.openlocfilehash: 9211af4726617598f3dd8772383cade6368e6c08
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007628"
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="ce31a-102">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="ce31a-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="ce31a-103">Предоставляет значения флагов, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="ce31a-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce31a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce31a-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ce31a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ce31a-105">Members</span></span>  
  
|<span data-ttu-id="ce31a-106">Член</span><span class="sxs-lookup"><span data-stu-id="ce31a-106">Member</span></span>|<span data-ttu-id="ce31a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ce31a-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="ce31a-108">Указывает, что флаги отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="ce31a-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="ce31a-109">Указывает `setLastError` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="ce31a-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="ce31a-110">Указывает `nomangle` ключевое слово.</span><span class="sxs-lookup"><span data-stu-id="ce31a-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="ce31a-111">Не используется.</span><span class="sxs-lookup"><span data-stu-id="ce31a-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce31a-112">Требования</span><span class="sxs-lookup"><span data-stu-id="ce31a-112">Requirements</span></span>  
 <span data-ttu-id="ce31a-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce31a-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce31a-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ce31a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce31a-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ce31a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce31a-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce31a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce31a-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ce31a-117">See also</span></span>

- [<span data-ttu-id="ce31a-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ce31a-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
