---
title: Перечисление CorSaveSize
ms.date: 03/30/2017
api_name:
- CorSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSaveSize
helpviewer_keywords:
- CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type:
- apiref
ms.openlocfilehash: 22a7f87a5803dc185052a5ce7ed427eff9f8fb18
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009188"
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="bbe96-102">Перечисление CorSaveSize</span><span class="sxs-lookup"><span data-stu-id="bbe96-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="bbe96-103">Содержит значения, указывающие уровень точности, необходимый при запросе размера операции сохранения.</span><span class="sxs-lookup"><span data-stu-id="bbe96-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbe96-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bbe96-104">Syntax</span></span>  
  
```cpp  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,
    cssQuick                   = 0x0001,
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="bbe96-105">Участники</span><span class="sxs-lookup"><span data-stu-id="bbe96-105">Members</span></span>  
  
|<span data-ttu-id="bbe96-106">Член</span><span class="sxs-lookup"><span data-stu-id="bbe96-106">Member</span></span>|<span data-ttu-id="bbe96-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bbe96-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="bbe96-108">Указывает, что возвращаемое значение должно быть точным.</span><span class="sxs-lookup"><span data-stu-id="bbe96-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="bbe96-109">Указывает, что возвращаемое значение должно быть оценено.</span><span class="sxs-lookup"><span data-stu-id="bbe96-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="bbe96-110">Указывает, что удаляемые типы должны быть удалены.</span><span class="sxs-lookup"><span data-stu-id="bbe96-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bbe96-111">Требования</span><span class="sxs-lookup"><span data-stu-id="bbe96-111">Requirements</span></span>  
 <span data-ttu-id="bbe96-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbe96-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbe96-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="bbe96-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="bbe96-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="bbe96-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bbe96-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbe96-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbe96-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="bbe96-116">See also</span></span>

- [<span data-ttu-id="bbe96-117">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="bbe96-117">Metadata Enumerations</span></span>](metadata-enumerations.md)
