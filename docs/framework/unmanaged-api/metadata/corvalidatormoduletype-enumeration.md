---
title: Перечисление CorValidatorModuleType
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
ms.openlocfilehash: 2fb7f11677870f7d53439f1867f167fabe70b22a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723861"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="6b3d2-102">Перечисление CorValidatorModuleType</span><span class="sxs-lookup"><span data-stu-id="6b3d2-102">CorValidatorModuleType Enumeration</span></span>

<span data-ttu-id="6b3d2-103">Указывает тип модуля.</span><span class="sxs-lookup"><span data-stu-id="6b3d2-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b3d2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6b3d2-104">Syntax</span></span>  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="6b3d2-105">Члены</span><span class="sxs-lookup"><span data-stu-id="6b3d2-105">Members</span></span>  
  
|<span data-ttu-id="6b3d2-106">Член</span><span class="sxs-lookup"><span data-stu-id="6b3d2-106">Member</span></span>|<span data-ttu-id="6b3d2-107">Описание</span><span class="sxs-lookup"><span data-stu-id="6b3d2-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="6b3d2-108">Недопустимый тип модуля.</span><span class="sxs-lookup"><span data-stu-id="6b3d2-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="6b3d2-109">Минимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="6b3d2-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="6b3d2-110">Модуль является переносимым исполняемым файлом (PE).</span><span class="sxs-lookup"><span data-stu-id="6b3d2-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="6b3d2-111">Модуль является OBJ-файлом.</span><span class="sxs-lookup"><span data-stu-id="6b3d2-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="6b3d2-112">Модуль является сеансом отладчика "изменить и продолжить".</span><span class="sxs-lookup"><span data-stu-id="6b3d2-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="6b3d2-113">Модуль — это один из инкрементно построенных.</span><span class="sxs-lookup"><span data-stu-id="6b3d2-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="6b3d2-114">Максимальное значение `CorValidatorModuleType` перечисления.</span><span class="sxs-lookup"><span data-stu-id="6b3d2-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b3d2-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6b3d2-115">Requirements</span></span>  

 <span data-ttu-id="6b3d2-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b3d2-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b3d2-117">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6b3d2-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b3d2-118">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6b3d2-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b3d2-119">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b3d2-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b3d2-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6b3d2-120">See also</span></span>

- [<span data-ttu-id="6b3d2-121">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="6b3d2-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
