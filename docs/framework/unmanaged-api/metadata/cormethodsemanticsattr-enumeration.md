---
description: Дополнительные сведения о перечислении Кормесодсемантиксаттр
title: Перечисление CorMethodSemanticsAttr
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 4079e81ae2389ff0684fd11d0751b191a7289932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784370"
---
# <a name="cormethodsemanticsattr-enumeration"></a>Перечисление CorMethodSemanticsAttr

Содержит значения, описывающие связь между методом и соответствующим свойством или событием.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`msSetter`|Указывает, что метод является методом `set` доступа для свойства.|  
|`msGetter`|Указывает, что метод является методом `get` доступа для свойства.|  
|`msOther`|Указывает, что метод имеет связь со свойством или событием, отличным от указанных здесь.|  
|`msAddOn`|Указывает, что метод добавляет методы обработчика для события.|  
|`msRemoveOn`|Указывает, что метод удаляет методы обработчика для события.|  
|`msFire`|Указывает, что метод вызывает событие.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)
