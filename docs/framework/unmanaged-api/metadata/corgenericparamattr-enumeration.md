---
title: Перечисление CorGenericParamAttr
ms.date: 03/30/2017
api_name:
- CorGenericParamAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGenericParamAttr
helpviewer_keywords:
- CorGenericParamAttr enumeration [.NET Framework metadata]
ms.assetid: 36c76266-71d8-48dc-bd89-54943fa659c1
topic_type:
- apiref
ms.openlocfilehash: ea50430c3ae6cef9b47880bcb8ad969f62ce9c39
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95704920"
---
# <a name="corgenericparamattr-enumeration"></a><span data-ttu-id="95e9e-102">Перечисление CorGenericParamAttr</span><span class="sxs-lookup"><span data-stu-id="95e9e-102">CorGenericParamAttr Enumeration</span></span>

<span data-ttu-id="95e9e-103">Содержит значения, описывающие <xref:System.Type> параметры для универсальных типов, которые используются в вызовах [IMetaDataEmit2::D ефинеженерикпарам](imetadataemit2-definegenericparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="95e9e-103">Contains values that describe the <xref:System.Type> parameters for generic types, as used in calls to [IMetaDataEmit2::DefineGenericParam](imetadataemit2-definegenericparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e9e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="95e9e-104">Syntax</span></span>  
  
```cpp  
typedef enum CorGenericParamAttr {  
  
    gpVarianceMask                     =   0x0003,  
    gpNonVariant                       =   0x0000,
    gpCovariant                        =   0x0001,  
    gpContravariant                    =   0x0002,  
  
    gpSpecialConstraintMask            =   0x001C,  
    gpNoSpecialConstraint              =   0x0000,  
    gpReferenceTypeConstraint          =   0x0004,
    gpNotNullableValueTypeConstraint   =   0x0008,  
    gpDefaultConstructorConstraint     =   0x0010  
  
} CorGenericParamAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="95e9e-105">Члены</span><span class="sxs-lookup"><span data-stu-id="95e9e-105">Members</span></span>  
  
|<span data-ttu-id="95e9e-106">Член</span><span class="sxs-lookup"><span data-stu-id="95e9e-106">Member</span></span>|<span data-ttu-id="95e9e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="95e9e-107">Description</span></span>|  
|------------|-----------------|  
|`gpVarianceMask`|<span data-ttu-id="95e9e-108">Дисперсия параметров применяется только к универсальным параметрам для интерфейсов и делегатов.</span><span class="sxs-lookup"><span data-stu-id="95e9e-108">Parameter variance applies only to generic parameters for interfaces and delegates.</span></span>|  
|`gpNonVariant`|<span data-ttu-id="95e9e-109">Указывает отсутствие дисперсии.</span><span class="sxs-lookup"><span data-stu-id="95e9e-109">Indicates the absence of variance.</span></span>|  
|`gpCovariant`|<span data-ttu-id="95e9e-110">Указывает ковариацию.</span><span class="sxs-lookup"><span data-stu-id="95e9e-110">Indicates covariance.</span></span>|  
|`gpContravariant`|<span data-ttu-id="95e9e-111">Указывает контрвариация.</span><span class="sxs-lookup"><span data-stu-id="95e9e-111">Indicates contravariance.</span></span>|  
|`gpSpecialConstraintMask`|<span data-ttu-id="95e9e-112">К любому параметру могут применяться специальные ограничения <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="95e9e-112">Special constraints can apply to any <xref:System.Type> parameter.</span></span>|  
|`gpNoSpecialConstraint`|<span data-ttu-id="95e9e-113">Указывает, что ограничение не применяется к <xref:System.Type> параметру.</span><span class="sxs-lookup"><span data-stu-id="95e9e-113">Indicates that no constraint applies to the <xref:System.Type> parameter.</span></span>|  
|`gpReferenceTypeConstraint`|<span data-ttu-id="95e9e-114">Указывает, что <xref:System.Type> параметр должен быть ссылочным типом.</span><span class="sxs-lookup"><span data-stu-id="95e9e-114">Indicates that the <xref:System.Type> parameter must be a reference type.</span></span>|  
|`gpNotNullableValueTypeConstraint`|<span data-ttu-id="95e9e-115">Указывает, что <xref:System.Type> параметр должен быть типом значения, который не может иметь значение null.</span><span class="sxs-lookup"><span data-stu-id="95e9e-115">Indicates that the <xref:System.Type> parameter must be a value type that cannot be a null value.</span></span>|  
|`gpDefaultConstructorConstraint`|<span data-ttu-id="95e9e-116">Указывает, что <xref:System.Type> параметр должен иметь открытый конструктор по умолчанию, который не принимает параметров.</span><span class="sxs-lookup"><span data-stu-id="95e9e-116">Indicates that the <xref:System.Type> parameter must have a default public constructor that takes no parameters.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="95e9e-117">Требования</span><span class="sxs-lookup"><span data-stu-id="95e9e-117">Requirements</span></span>  

 <span data-ttu-id="95e9e-118">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95e9e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e9e-119">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="95e9e-119">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="95e9e-120">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e9e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95e9e-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="95e9e-121">See also</span></span>

- [<span data-ttu-id="95e9e-122">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="95e9e-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
