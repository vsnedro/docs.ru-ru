---
title: Перечисление CorPEKind
ms.date: 03/30/2017
api_name:
- CorPEKind
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPEKind
helpviewer_keywords:
- CorPEKind enumeration [.NET Framework metadata]
ms.assetid: 22dc6dea-b1b9-4982-a730-a022d586b117
topic_type:
- apiref
ms.openlocfilehash: 001be0c5e8897bacf76d2a044fb9400768473052
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673544"
---
# <a name="corpekind-enumeration"></a><span data-ttu-id="e8a7d-102">Перечисление CorPEKind</span><span class="sxs-lookup"><span data-stu-id="e8a7d-102">CorPEKind Enumeration</span></span>

<span data-ttu-id="e8a7d-103">Содержит значения, описывающие переносимый исполняемый файл (PE), возвращенный при вызове [IMetaDataImport2:: GetPEKind](imetadataimport2-getpekind-method.md).</span><span class="sxs-lookup"><span data-stu-id="e8a7d-103">Contains values that describe a portable executable (PE) file, as returned from a call to [IMetaDataImport2::GetPEKind](imetadataimport2-getpekind-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a7d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8a7d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPEKind {  
  
    peNot           = 0x00000000,  
    peILonly        = 0x00000001,  
    pe32BitRequired = 0x00000002,  
    pe32Plus        = 0x00000004,  
    pe32Unmanaged   = 0x00000008,  
    pe32BitPreferred= 0x00000010  
  
} CorPEKind;  
```  
  
## <a name="members"></a><span data-ttu-id="e8a7d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e8a7d-105">Members</span></span>  
  
|<span data-ttu-id="e8a7d-106">Член</span><span class="sxs-lookup"><span data-stu-id="e8a7d-106">Member</span></span>|<span data-ttu-id="e8a7d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e8a7d-107">Description</span></span>|  
|------------|-----------------|  
|`peNot`|<span data-ttu-id="e8a7d-108">Указывает, что этот файл не является PE-файлом.</span><span class="sxs-lookup"><span data-stu-id="e8a7d-108">Indicates that this is not a PE file.</span></span>|  
|`peILOnly`|<span data-ttu-id="e8a7d-109">Указывает, что этот PE файл содержит только управляемый код.</span><span class="sxs-lookup"><span data-stu-id="e8a7d-109">Indicates that this PE file contains only managed code.</span></span>|  
|`pe32BitRequired`|<span data-ttu-id="e8a7d-110">Указывает, что этот PE файл выполняет вызовы Win32.</span><span class="sxs-lookup"><span data-stu-id="e8a7d-110">Indicates that this PE file makes Win32 calls.</span></span>|  
|`pe32Plus`|<span data-ttu-id="e8a7d-111">Указывает, что этот PE-файл выполняется на 64-разрядной платформе.</span><span class="sxs-lookup"><span data-stu-id="e8a7d-111">Indicates that this PE file runs on a 64-bit platform.</span></span>|  
|`pe32Unmanaged`|<span data-ttu-id="e8a7d-112">Указывает, что этот PE-файл является машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="e8a7d-112">Indicates that this PE file is native code.</span></span>|  
|<span data-ttu-id="e8a7d-113">pe32BitPreferred</span><span class="sxs-lookup"><span data-stu-id="e8a7d-113">pe32BitPreferred</span></span>|<span data-ttu-id="e8a7d-114">Указывает, что этот PE-файл является нейтральным к платформе и предпочитает загрузку в 32-разрядной среде.</span><span class="sxs-lookup"><span data-stu-id="e8a7d-114">Indicates that this PE file is platform-neutral and prefers to be loaded in a 32-bit environment.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8a7d-115">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e8a7d-115">Remarks</span></span>  

 <span data-ttu-id="e8a7d-116">Эти значения можно использовать в побитовых сочетаниях.</span><span class="sxs-lookup"><span data-stu-id="e8a7d-116">These values can be used in bitwise combinations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a7d-117">Требования</span><span class="sxs-lookup"><span data-stu-id="e8a7d-117">Requirements</span></span>  

 <span data-ttu-id="e8a7d-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8a7d-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8a7d-119">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="e8a7d-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e8a7d-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8a7d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a7d-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e8a7d-121">See also</span></span>

- [<span data-ttu-id="e8a7d-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="e8a7d-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
