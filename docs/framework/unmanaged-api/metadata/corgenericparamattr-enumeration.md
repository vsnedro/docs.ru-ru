---
description: Дополнительные сведения о перечислении Корженерикпараматтр
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
ms.openlocfilehash: 8fe8cb20834ecbc5477bbe8b01bf77d6b1af0eea
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784461"
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
  
## <a name="members"></a>Члены  
  
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
