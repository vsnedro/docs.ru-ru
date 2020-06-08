---
title: Перечисление COR_PRF_STATIC_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
ms.openlocfilehash: 80d72aefc736054afcee152c55e941c0f8f3c6a8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500771"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="b6b27-102">Перечисление COR_PRF_STATIC_TYPE</span><span class="sxs-lookup"><span data-stu-id="b6b27-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="b6b27-103">Указывает, является ли поле статическим и, если да, относящееся к этому полю статическое качество.</span><span class="sxs-lookup"><span data-stu-id="b6b27-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="b6b27-104">Эти значения можно комбинировать с помощью побитовой операции OR, чтобы указать, что поле имеет несколько различных статических качеств.</span><span class="sxs-lookup"><span data-stu-id="b6b27-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b27-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b6b27-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="b6b27-106">Участники</span><span class="sxs-lookup"><span data-stu-id="b6b27-106">Members</span></span>  
  
|<span data-ttu-id="b6b27-107">Член</span><span class="sxs-lookup"><span data-stu-id="b6b27-107">Member</span></span>|<span data-ttu-id="b6b27-108">Описание</span><span class="sxs-lookup"><span data-stu-id="b6b27-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="b6b27-109">Поле не является статическим.</span><span class="sxs-lookup"><span data-stu-id="b6b27-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="b6b27-110">Поле является статическим в домене приложения.</span><span class="sxs-lookup"><span data-stu-id="b6b27-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="b6b27-111">Поле является статическим для потока.</span><span class="sxs-lookup"><span data-stu-id="b6b27-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="b6b27-112">Поле является статическим по контексту.</span><span class="sxs-lookup"><span data-stu-id="b6b27-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="b6b27-113">Поле является относительным виртуальным адресом (RVA) — статическим.</span><span class="sxs-lookup"><span data-stu-id="b6b27-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b6b27-114">Требования</span><span class="sxs-lookup"><span data-stu-id="b6b27-114">Requirements</span></span>  
 <span data-ttu-id="b6b27-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6b27-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b27-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b6b27-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b6b27-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6b27-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6b27-118">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b27-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b27-119">См. также</span><span class="sxs-lookup"><span data-stu-id="b6b27-119">See also</span></span>

- [<span data-ttu-id="b6b27-120">Перечисления профилирования</span><span class="sxs-lookup"><span data-stu-id="b6b27-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
