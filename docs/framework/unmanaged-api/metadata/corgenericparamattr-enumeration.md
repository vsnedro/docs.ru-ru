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
ms.openlocfilehash: ea84b742c901ba58a3bb730f1f5033a0d90610ce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007381"
---
# <a name="corgenericparamattr-enumeration"></a>Перечисление CorGenericParamAttr
Содержит значения, описывающие <xref:System.Type> параметры для универсальных типов, которые используются в вызовах [IMetaDataEmit2::D ефинеженерикпарам](imetadataemit2-definegenericparam-method.md).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`gpVarianceMask`|Дисперсия параметров применяется только к универсальным параметрам для интерфейсов и делегатов.|  
|`gpNonVariant`|Указывает отсутствие дисперсии.|  
|`gpCovariant`|Указывает ковариацию.|  
|`gpContravariant`|Указывает контрвариация.|  
|`gpSpecialConstraintMask`|К любому параметру могут применяться специальные ограничения <xref:System.Type> .|  
|`gpNoSpecialConstraint`|Указывает, что ограничение не применяется к <xref:System.Type> параметру.|  
|`gpReferenceTypeConstraint`|Указывает, что <xref:System.Type> параметр должен быть ссылочным типом.|  
|`gpNotNullableValueTypeConstraint`|Указывает, что <xref:System.Type> параметр должен быть типом значения, который не может иметь значение null.|  
|`gpDefaultConstructorConstraint`|Указывает, что <xref:System.Type> параметр должен иметь открытый конструктор по умолчанию, который не принимает параметров.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
