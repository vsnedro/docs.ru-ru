---
title: Перечисление CorUnmanagedCallingConvention
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: b4c521489f38360d45c2cf8ff3780e057299f0b4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008954"
---
# <a name="corunmanagedcallingconvention-enumeration"></a><span data-ttu-id="3b57d-102">Перечисление CorUnmanagedCallingConvention</span><span class="sxs-lookup"><span data-stu-id="3b57d-102">CorUnmanagedCallingConvention Enumeration</span></span>
<span data-ttu-id="3b57d-103">Указывает соглашения о вызовах для неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="3b57d-103">Specifies the calling conventions for unmanaged code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b57d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3b57d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a><span data-ttu-id="3b57d-105">Участники</span><span class="sxs-lookup"><span data-stu-id="3b57d-105">Members</span></span>  
  
|<span data-ttu-id="3b57d-106">Член</span><span class="sxs-lookup"><span data-stu-id="3b57d-106">Member</span></span>|<span data-ttu-id="3b57d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="3b57d-107">Description</span></span>|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|<span data-ttu-id="3b57d-108">Соглашение о вызовах языка C.</span><span class="sxs-lookup"><span data-stu-id="3b57d-108">The C language calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|<span data-ttu-id="3b57d-109">Стандартное соглашение о вызовах.</span><span class="sxs-lookup"><span data-stu-id="3b57d-109">The standard calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|<span data-ttu-id="3b57d-110">Соглашение о вызовах "this".</span><span class="sxs-lookup"><span data-stu-id="3b57d-110">The "this" calling convention.</span></span>|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|<span data-ttu-id="3b57d-111">Соглашение о вызовах "Fast".</span><span class="sxs-lookup"><span data-stu-id="3b57d-111">The "fast" calling convention.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_C`|<span data-ttu-id="3b57d-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="3b57d-112">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|<span data-ttu-id="3b57d-113">Не используется.</span><span class="sxs-lookup"><span data-stu-id="3b57d-113">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|<span data-ttu-id="3b57d-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="3b57d-114">Not used.</span></span>|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|<span data-ttu-id="3b57d-115">Не используется.</span><span class="sxs-lookup"><span data-stu-id="3b57d-115">Not used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3b57d-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="3b57d-116">Remarks</span></span>  
 <span data-ttu-id="3b57d-117">Среда CLR не поддерживает "быстрое" соглашение о вызовах в .NET Framework версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="3b57d-117">The CLR does not support the "fast" calling convention in the .NET Framework version 1.0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b57d-118">Требования</span><span class="sxs-lookup"><span data-stu-id="3b57d-118">Requirements</span></span>  
 <span data-ttu-id="3b57d-119">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b57d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b57d-120">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="3b57d-120">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="3b57d-121">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b57d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b57d-122">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3b57d-122">See also</span></span>

- [<span data-ttu-id="3b57d-123">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="3b57d-123">Metadata Enumerations</span></span>](metadata-enumerations.md)
