---
title: Перечисление CorPropertyAttr
ms.date: 03/30/2017
api_name:
- CorPropertyAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorPropertyAttr
helpviewer_keywords:
- CorPropertyAttr enumeration [.NET Framework metadata]
ms.assetid: 58ac8202-854d-4efd-acfb-d2da8b446e12
topic_type:
- apiref
ms.openlocfilehash: b6651f30e0df3a5ffc29d310b9067e76761dcf01
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007537"
---
# <a name="corpropertyattr-enumeration"></a><span data-ttu-id="45972-102">Перечисление CorPropertyAttr</span><span class="sxs-lookup"><span data-stu-id="45972-102">CorPropertyAttr Enumeration</span></span>
<span data-ttu-id="45972-103">Содержит значения, описывающие метаданные свойства.</span><span class="sxs-lookup"><span data-stu-id="45972-103">Contains values that describe the metadata of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45972-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45972-104">Syntax</span></span>  
  
```cpp  
typedef enum CorPropertyAttr {  
  
    prSpecialName           =   0x0200,
    prReservedMask          =   0xf400,  
    prRTSpecialName         =   0x0400,  
    prHasDefault            =   0x1000,  
    prUnused                =   0xe9ff  
  
} CorPropertyAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="45972-105">Участники</span><span class="sxs-lookup"><span data-stu-id="45972-105">Members</span></span>  
  
|<span data-ttu-id="45972-106">Член</span><span class="sxs-lookup"><span data-stu-id="45972-106">Member</span></span>|<span data-ttu-id="45972-107">Описание</span><span class="sxs-lookup"><span data-stu-id="45972-107">Description</span></span>|  
|------------|-----------------|  
|`prSpecialName`|<span data-ttu-id="45972-108">Указывает, что свойство является специальным, и что его имя описывает, как это делать.</span><span class="sxs-lookup"><span data-stu-id="45972-108">Specifies that the property is special, and that its name describes how.</span></span>|  
|`prReservedMask`|<span data-ttu-id="45972-109">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="45972-109">Reserved for internal use by the common language runtime.</span></span>|  
|`prRTSpecialName`|<span data-ttu-id="45972-110">Указывает, что внутренние API метаданных среды CLR должны проверять кодировку имени свойства.</span><span class="sxs-lookup"><span data-stu-id="45972-110">Specifies that the common language runtime metadata internal APIs should check the encoding of the property name.</span></span>|  
|`prHasDefault`|<span data-ttu-id="45972-111">Указывает, что свойство имеет значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="45972-111">Specifies that the property has a default value.</span></span>|  
|`prUnused`|<span data-ttu-id="45972-112">Не используется.</span><span class="sxs-lookup"><span data-stu-id="45972-112">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45972-113">Требования</span><span class="sxs-lookup"><span data-stu-id="45972-113">Requirements</span></span>  
 <span data-ttu-id="45972-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45972-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45972-115">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="45972-115">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="45972-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45972-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45972-117">См. также статью</span><span class="sxs-lookup"><span data-stu-id="45972-117">See also</span></span>

- [<span data-ttu-id="45972-118">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="45972-118">Metadata Enumerations</span></span>](metadata-enumerations.md)
