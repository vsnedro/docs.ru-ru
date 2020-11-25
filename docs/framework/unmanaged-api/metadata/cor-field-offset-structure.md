---
title: Структура COR_FIELD_OFFSET
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
ms.openlocfilehash: 1a8ab5aa5909af60089d5e4cc8092e15bc75e8cc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724186"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="75c50-102">Структура COR_FIELD_OFFSET</span><span class="sxs-lookup"><span data-stu-id="75c50-102">COR_FIELD_OFFSET Structure</span></span>

<span data-ttu-id="75c50-103">Хранит смещение указанного поля в пределах класса.</span><span class="sxs-lookup"><span data-stu-id="75c50-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75c50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75c50-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="75c50-105">Члены</span><span class="sxs-lookup"><span data-stu-id="75c50-105">Members</span></span>  
  
|<span data-ttu-id="75c50-106">Член</span><span class="sxs-lookup"><span data-stu-id="75c50-106">Member</span></span>|<span data-ttu-id="75c50-107">Описание</span><span class="sxs-lookup"><span data-stu-id="75c50-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="75c50-108">`mdFieldDef`Токен метаданных, представляющий поле.</span><span class="sxs-lookup"><span data-stu-id="75c50-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="75c50-109">Смещение поля в его классе.</span><span class="sxs-lookup"><span data-stu-id="75c50-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75c50-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="75c50-110">Remarks</span></span>  

 <span data-ttu-id="75c50-111">Методы [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) и [IMetaDataEmit:: сеткласслайаут](imetadataemit-setclasslayout-method.md) принимают параметр типа `COR_FIELD_OFFSET` .</span><span class="sxs-lookup"><span data-stu-id="75c50-111">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75c50-112">Требования</span><span class="sxs-lookup"><span data-stu-id="75c50-112">Requirements</span></span>  

 <span data-ttu-id="75c50-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75c50-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75c50-114">**Заголовок:** Корхдр. h, CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="75c50-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="75c50-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75c50-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c50-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="75c50-116">See also</span></span>

- [<span data-ttu-id="75c50-117">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="75c50-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="75c50-118">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="75c50-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="75c50-119">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="75c50-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
