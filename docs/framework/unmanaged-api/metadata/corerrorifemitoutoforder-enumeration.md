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
ms.openlocfilehash: 1d1b0cbb8be33f285b63e7353da973455e0fd752
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718856"
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
  
## <a name="members"></a>Члены  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)
