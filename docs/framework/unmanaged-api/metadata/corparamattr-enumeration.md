---
description: Дополнительные сведения о перечислении Корпараматтр
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
ms.openlocfilehash: c07569d3fb92b20a7985dbfeb2205af727866051
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784292"
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
  
## <a name="members"></a>Члены  
  
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
