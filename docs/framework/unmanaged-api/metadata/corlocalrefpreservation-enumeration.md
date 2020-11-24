---
title: Перечисление CorLocalRefPreservation
ms.date: 03/30/2017
api_name:
- CorLocalRefPreservation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorLocalRefPreservation
helpviewer_keywords:
- CorLocalRefPreservation enumeration [.NET Framework metadata]
ms.assetid: 44757163-1228-4213-a4c4-d4de503cc75d
topic_type:
- apiref
ms.openlocfilehash: 49b0298f4fa776c93f89ac380ce65568b493379b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677119"
---
# <a name="corlocalrefpreservation-enumeration"></a><span data-ttu-id="65f6b-102">Перечисление CorLocalRefPreservation</span><span class="sxs-lookup"><span data-stu-id="65f6b-102">CorLocalRefPreservation Enumeration</span></span>

<span data-ttu-id="65f6b-103">Содержит значения флага для обработки локальных ссылок.</span><span class="sxs-lookup"><span data-stu-id="65f6b-103">Contains flag values for the treatment of local references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65f6b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="65f6b-104">Syntax</span></span>  
  
```cpp  
typedef enum CorLocalRefPreservation  
{  
    MDPreserveLocalRefsNone     =   0x00000000,  
    MDPreserveLocalTypeRef      =   0x00000001,  
    MDPreserveLocalMemberRef    =   0x00000002  
} CorLocalRefPreservation;  
```  
  
## <a name="members"></a><span data-ttu-id="65f6b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="65f6b-105">Members</span></span>  
  
|<span data-ttu-id="65f6b-106">Член</span><span class="sxs-lookup"><span data-stu-id="65f6b-106">Member</span></span>|<span data-ttu-id="65f6b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="65f6b-107">Description</span></span>|  
|------------|-----------------|  
|`MDPreserveLocalRefsNone`|<span data-ttu-id="65f6b-108">Не сохранять локальные ссылки.</span><span class="sxs-lookup"><span data-stu-id="65f6b-108">Preserve no local references.</span></span>|  
|`MDPreserveLocalTypeRef`|<span data-ttu-id="65f6b-109">Сохранение ссылок на локальные типы.</span><span class="sxs-lookup"><span data-stu-id="65f6b-109">Preserve local type references.</span></span>|  
|`MDPreserveLocalMemberRef`|<span data-ttu-id="65f6b-110">Сохранение ссылок на локальные члены.</span><span class="sxs-lookup"><span data-stu-id="65f6b-110">Preserve local member references.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65f6b-111">Требования</span><span class="sxs-lookup"><span data-stu-id="65f6b-111">Requirements</span></span>  

 <span data-ttu-id="65f6b-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65f6b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65f6b-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="65f6b-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="65f6b-114">**.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65f6b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f6b-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="65f6b-115">See also</span></span>

- [<span data-ttu-id="65f6b-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="65f6b-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
