---
title: Перечисление CeeSectionAttr
ms.date: 03/30/2017
api_name:
- CeeSectionAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionAttr
helpviewer_keywords:
- CeeSectionAttr enumeration [.NET Framework metadata]
ms.assetid: 0db51881-b869-4677-a715-1726a9216489
topic_type:
- apiref
ms.openlocfilehash: 6da8a111f716906e403d85bc0b1a29eba7238100
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006068"
---
# <a name="ceesectionattr-enumeration"></a><span data-ttu-id="099ad-102">Перечисление CeeSectionAttr</span><span class="sxs-lookup"><span data-stu-id="099ad-102">CeeSectionAttr Enumeration</span></span>
<span data-ttu-id="099ad-103">Предоставляет значения, указывающие атрибуты раздела для использования интерфейсом [ICeeGen](iceegen-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="099ad-103">Provides values that specify attributes of a section for use by the [ICeeGen](iceegen-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="099ad-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="099ad-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    sdNone      = 0,  
    sdReadOnly  = IMAGE_SCN_CNT_INITIALIZED_DATA |  
                  IMAGE_SCN_MEM_READ,  
    sdReadWrite = sdReadOnly | IMAGE_SCN_MEM_WRITE,  
    sdExecute   = IMAGE_SCN_MEM_READ | IMAGE_SCN_CNT_CODE |  
                  IMAGE_SCN_MEM_EXECUTE  
} CeeSectionAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="099ad-105">Участники</span><span class="sxs-lookup"><span data-stu-id="099ad-105">Members</span></span>  
  
|<span data-ttu-id="099ad-106">Член</span><span class="sxs-lookup"><span data-stu-id="099ad-106">Member</span></span>|<span data-ttu-id="099ad-107">Описание</span><span class="sxs-lookup"><span data-stu-id="099ad-107">Description</span></span>|  
|------------|-----------------|  
|`sdNone`|<span data-ttu-id="099ad-108">Раздел не имеет атрибутов.</span><span class="sxs-lookup"><span data-stu-id="099ad-108">Section has no attributes.</span></span>|  
|`sdReadOnly`|<span data-ttu-id="099ad-109">Раздел содержит инициализированные данные, которые могут быть только считаны, но не обновлены.</span><span class="sxs-lookup"><span data-stu-id="099ad-109">Section contains initialized data that can be only read, not updated.</span></span>|  
|`sdReadWrite`|<span data-ttu-id="099ad-110">Раздел содержит инициализированные данные, которые могут быть считаны или обновлены.</span><span class="sxs-lookup"><span data-stu-id="099ad-110">Section contains initialized data that can be read or updated.</span></span>|  
|`sdExecute`|<span data-ttu-id="099ad-111">Раздел содержит исполняемый код, который может быть прочитан и выполнен.</span><span class="sxs-lookup"><span data-stu-id="099ad-111">Section contains executable code that is allowed to be read and executed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="099ad-112">Требования</span><span class="sxs-lookup"><span data-stu-id="099ad-112">Requirements</span></span>  
 <span data-ttu-id="099ad-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="099ad-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="099ad-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="099ad-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="099ad-115">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="099ad-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="099ad-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="099ad-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="099ad-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="099ad-117">See also</span></span>

- [<span data-ttu-id="099ad-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="099ad-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
