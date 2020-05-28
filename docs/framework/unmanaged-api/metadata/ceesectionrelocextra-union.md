---
title: Объединение CeeSectionRelocExtra
ms.date: 03/30/2017
api_name:
- CeeSectionRelocExtra Union
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocExtra
helpviewer_keywords:
- CeeSectionRelocExtra union [.NET Framework metadata]
ms.assetid: d9568cf6-7f98-4cd6-ab36-0a2bd509afcc
topic_type:
- apiref
ms.openlocfilehash: d11fefe220fdb00457cc48a6cd166673350be049
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006040"
---
# <a name="ceesectionrelocextra-union"></a><span data-ttu-id="a176d-102">Объединение CeeSectionRelocExtra</span><span class="sxs-lookup"><span data-stu-id="a176d-102">CeeSectionRelocExtra Union</span></span>
<span data-ttu-id="a176d-103">Представляет смещение адреса, используемое интерфейсом [ICeeGen](iceegen-interface.md) для перемещения раздела.</span><span class="sxs-lookup"><span data-stu-id="a176d-103">Represents an address offset that is used by the [ICeeGen](iceegen-interface.md) interface to relocate a section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a176d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a176d-104">Syntax</span></span>  
  
```cpp  
typedef union  {  
    USHORT highAdj;  
} CeeSectionRelocExtra;  
```  
  
## <a name="members"></a><span data-ttu-id="a176d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="a176d-105">Members</span></span>  
  
|<span data-ttu-id="a176d-106">Член</span><span class="sxs-lookup"><span data-stu-id="a176d-106">Member</span></span>|<span data-ttu-id="a176d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="a176d-107">Description</span></span>|  
|------------|-----------------|  
|`highAdj`|<span data-ttu-id="a176d-108">Корректировка верхнего адреса для раздела.</span><span class="sxs-lookup"><span data-stu-id="a176d-108">The upper address adjustment for the section.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a176d-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a176d-109">Requirements</span></span>  
 <span data-ttu-id="a176d-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a176d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a176d-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a176d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a176d-112">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a176d-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a176d-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a176d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a176d-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a176d-114">See also</span></span>

- [<span data-ttu-id="a176d-115">Объединения метаданных</span><span class="sxs-lookup"><span data-stu-id="a176d-115">Metadata Unions</span></span>](metadata-unions.md)
