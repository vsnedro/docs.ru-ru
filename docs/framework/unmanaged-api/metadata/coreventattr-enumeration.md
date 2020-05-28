---
title: Перечисление CorEventAttr
ms.date: 03/30/2017
api_name:
- CorEventAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorEventAttr
helpviewer_keywords:
- CorEventAttr enumeration [.NET Framework metadata]
ms.assetid: dc2b3281-3820-487e-930d-350b66dc6417
topic_type:
- apiref
ms.openlocfilehash: e22b390271a7813dd1d34aecf5f8a62d7eb81005
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007444"
---
# <a name="coreventattr-enumeration"></a>Перечисление CorEventAttr
Содержит значения, описывающие метаданные события.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorEventAttr {  
  
    evSpecialName           =   0x0200,  
  
    evReservedMask          =   0x0400,  
    evRTSpecialName         =   0x0400,  
  
} CorEventAttr;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`evSpecialName`|Указывает, что событие является специальным, и что его имя описывает, как это делать.|  
|`evReservedMask`|Зарезервировано для внутреннего использования средой CLR.|  
|`evRTSpecialName`|Указывает, что среда CLR должна проверять кодировку имени события.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
