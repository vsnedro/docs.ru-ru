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
ms.openlocfilehash: e8afcb972cab9757458c7032c3678d45c6418fac
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007576"
---
# <a name="corparamattr-enumeration"></a>Перечисление CorParamAttr
Содержит значения, описывающие метаданные параметра метода.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`pdIn`|Указывает, что параметр передается в вызов метода.|  
|`pdOut`|Указывает, что параметр передается из возвращаемого методом значения.|  
|`pdOptional`|Указывает, что данный параметр не обязателен.|  
|`pdReservedMask`|Зарезервировано для внутреннего использования средой CLR.|  
|`pdHasDefault`|Указывает, что параметр имеет стандартное значение.|  
|`pdHasFieldMarshal`|Указывает, что параметр содержит сведения об упаковке.|  
|`pdUnused`|Не используется.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
