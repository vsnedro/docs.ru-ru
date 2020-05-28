---
title: MALLOC_TYPE - перечисление
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
ms.openlocfilehash: 630fe4e79b369bfdefc19be72780f1893090895e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008460"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="3bdb8-102">MALLOC_TYPE - перечисление</span><span class="sxs-lookup"><span data-stu-id="3bdb8-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="3bdb8-103">Содержит значения, указывающие характеристики выделяемой памяти.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bdb8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3bdb8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="3bdb8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3bdb8-105">Members</span></span>  
  
|<span data-ttu-id="3bdb8-106">Член</span><span class="sxs-lookup"><span data-stu-id="3bdb8-106">Member</span></span>|<span data-ttu-id="3bdb8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3bdb8-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="3bdb8-108">Выделенная память может содержать исполняемый файл.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="3bdb8-109">Выделенная память является потокобезопасной.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="3bdb8-110">То есть доступ к памяти может осуществляться несколькими потоками без синхронизации.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="3bdb8-111">Если этот флаг не установлен, вызовы для объекта должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="3bdb8-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3bdb8-112">Требования</span><span class="sxs-lookup"><span data-stu-id="3bdb8-112">Requirements</span></span>  
 <span data-ttu-id="3bdb8-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bdb8-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bdb8-114">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3bdb8-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bdb8-115">**Библиотека:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3bdb8-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bdb8-116">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bdb8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bdb8-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3bdb8-117">See also</span></span>

- [<span data-ttu-id="3bdb8-118">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="3bdb8-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
