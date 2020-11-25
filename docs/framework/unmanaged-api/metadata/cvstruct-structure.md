---
title: Структура CVStruct
ms.date: 03/30/2017
api_name:
- CVStruct
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CVStruct
helpviewer_keywords:
- CVStruct structure [.NET Framework metadata]
ms.assetid: e9e4e497-d5fb-464b-991c-3bdd824664fd
topic_type:
- apiref
ms.openlocfilehash: db36b94fafe20b58b9bcbb886b8d285326960f67
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715580"
---
# <a name="cvstruct-structure"></a><span data-ttu-id="59ab5-102">Структура CVStruct</span><span class="sxs-lookup"><span data-stu-id="59ab5-102">CVStruct Structure</span></span>

<span data-ttu-id="59ab5-103">Содержит сведения, используемые при установке модуля или составного образа.</span><span class="sxs-lookup"><span data-stu-id="59ab5-103">Contains information that is used when installing a module or a composite image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59ab5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59ab5-104">Syntax</span></span>  
  
```cpp  
typedef struct {  
    short Major;  
    short Minor;  
    short Sub;  
    short Build;  
} CVStruct;  
```  
  
## <a name="members"></a><span data-ttu-id="59ab5-105">Члены</span><span class="sxs-lookup"><span data-stu-id="59ab5-105">Members</span></span>  
  
|<span data-ttu-id="59ab5-106">Член</span><span class="sxs-lookup"><span data-stu-id="59ab5-106">Member</span></span>|<span data-ttu-id="59ab5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="59ab5-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="59ab5-108">Значительно</span><span class="sxs-lookup"><span data-stu-id="59ab5-108">Major</span></span>|<span data-ttu-id="59ab5-109">Номер сборки основного номера версии.</span><span class="sxs-lookup"><span data-stu-id="59ab5-109">Major version build number.</span></span>|  
|<span data-ttu-id="59ab5-110">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="59ab5-110">Minor</span></span>|<span data-ttu-id="59ab5-111">Номер сборки дополнительного номера версии.</span><span class="sxs-lookup"><span data-stu-id="59ab5-111">Minor version build number.</span></span>|  
|<span data-ttu-id="59ab5-112">Sub</span><span class="sxs-lookup"><span data-stu-id="59ab5-112">Sub</span></span>|<span data-ttu-id="59ab5-113">Номер подсборки.</span><span class="sxs-lookup"><span data-stu-id="59ab5-113">Sub-build number.</span></span>|  
|<span data-ttu-id="59ab5-114">Сборка</span><span class="sxs-lookup"><span data-stu-id="59ab5-114">Build</span></span>|<span data-ttu-id="59ab5-115">Номер сборки.</span><span class="sxs-lookup"><span data-stu-id="59ab5-115">Build number.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="59ab5-116">Требования</span><span class="sxs-lookup"><span data-stu-id="59ab5-116">Requirements</span></span>  

 <span data-ttu-id="59ab5-117">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="59ab5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59ab5-118">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="59ab5-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59ab5-119">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="59ab5-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="59ab5-120">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59ab5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59ab5-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="59ab5-121">See also</span></span>

- [<span data-ttu-id="59ab5-122">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="59ab5-122">Metadata Structures</span></span>](metadata-structures.md)
