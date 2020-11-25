---
title: Перечисление CorParamAttr
ms.date: 03/30/2017
api_name:
- CorParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorParamAttr
helpviewer_keywords:
- CorParamAttr enumeration [.NET Framework metadata]
ms.assetid: a7ff90ad-dad8-48e8-917d-4aa9a118cbc8
topic_type:
- apiref
ms.openlocfilehash: 6f5d022a96fa021cb28dbbb67d0b53e08f77498c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729293"
---
# <a name="corparamattr-enumeration"></a><span data-ttu-id="991ef-102">Перечисление CorParamAttr</span><span class="sxs-lookup"><span data-stu-id="991ef-102">CorParamAttr Enumeration</span></span>

<span data-ttu-id="991ef-103">Содержит значения, описывающие метаданные параметра метода.</span><span class="sxs-lookup"><span data-stu-id="991ef-103">Contains values that describe the metadata of a method parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="991ef-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="991ef-104">Syntax</span></span>  
  
```cpp  
typedef enum CorParamAttr {  
  
    pdIn                        =   0x0001,  
    pdOut                       =   0x0002,  
    pdOptional                  =   0x0010,  
  
    pdReservedMask              =   0xf000,  
    pdHasDefault                =   0x1000,  
    pdHasFieldMarshal           =   0x2000,  
  
    pdUnused                    =   0xcfe0  
  
} CorParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="991ef-105">Члены</span><span class="sxs-lookup"><span data-stu-id="991ef-105">Members</span></span>  
  
|<span data-ttu-id="991ef-106">Член</span><span class="sxs-lookup"><span data-stu-id="991ef-106">Member</span></span>|<span data-ttu-id="991ef-107">Описание</span><span class="sxs-lookup"><span data-stu-id="991ef-107">Description</span></span>|  
|------------|-----------------|  
|`pdIn`|<span data-ttu-id="991ef-108">Указывает, что параметр передается в вызов метода.</span><span class="sxs-lookup"><span data-stu-id="991ef-108">Specifies that the parameter is passed into the method call.</span></span>|  
|`pdOut`|<span data-ttu-id="991ef-109">Указывает, что параметр передается из возвращаемого методом значения.</span><span class="sxs-lookup"><span data-stu-id="991ef-109">Specifies that the parameter is passed from the method return.</span></span>|  
|`pdOptional`|<span data-ttu-id="991ef-110">Указывает, что данный параметр не обязателен.</span><span class="sxs-lookup"><span data-stu-id="991ef-110">Specifies that the parameter is optional.</span></span>|  
|`pdReservedMask`|<span data-ttu-id="991ef-111">Зарезервировано для внутреннего использования средой CLR.</span><span class="sxs-lookup"><span data-stu-id="991ef-111">Reserved for internal use by the common language runtime.</span></span>|  
|`pdHasDefault`|<span data-ttu-id="991ef-112">Указывает, что параметр имеет стандартное значение.</span><span class="sxs-lookup"><span data-stu-id="991ef-112">Specifies that the parameter has a default value.</span></span>|  
|`pdHasFieldMarshal`|<span data-ttu-id="991ef-113">Указывает, что параметр содержит сведения об упаковке.</span><span class="sxs-lookup"><span data-stu-id="991ef-113">Specifies that the parameter has marshaling information.</span></span>|  
|`pdUnused`|<span data-ttu-id="991ef-114">Не используется.</span><span class="sxs-lookup"><span data-stu-id="991ef-114">Unused.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="991ef-115">Требования</span><span class="sxs-lookup"><span data-stu-id="991ef-115">Requirements</span></span>  

 <span data-ttu-id="991ef-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="991ef-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="991ef-117">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="991ef-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="991ef-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="991ef-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991ef-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="991ef-119">See also</span></span>

- [<span data-ttu-id="991ef-120">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="991ef-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
