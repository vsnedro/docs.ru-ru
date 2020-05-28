---
title: Перечисление CorErrorIfEmitOutOfOrder
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: fec049297bfa12d86cb2a7f7950e84ae540832b1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007442"
---
# <a name="corerrorifemitoutoforder-enumeration"></a>Перечисление CorErrorIfEmitOutOfOrder
Содержит значения флагов, указывающие условия, при которых должно создаваться сообщение об ошибке при беспорядочном выводе метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|Указывает поведение по умолчанию, при котором не создаются сообщения об ошибках.|  
|`MDErrorOutOfOrderNone`|Указывает, что компилятор не должен создавать сообщения об ошибках.|  
|`MDErrorOutOfOrderAll`|Указывает, что компилятор должен создать сообщение об ошибке, когда поле, свойство, событие, метод или параметр выдаются в неопределенном порядке.|  
|`MDMethodOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке, если метод выдается не по порядку.|  
|`MDFieldOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке, если поле выдается не по порядку.|  
|`MDParamOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке, если параметр выдается не по порядку.|  
|`MDPropertyOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке, если свойство выдается не по порядку.|  
|`MDEventOutOfOrder`|Указывает, что компилятор должен создать сообщение об ошибке, если событие выдается не по порядку.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Перечисления метаданных](metadata-enumerations.md)
