---
description: 'Дополнительные сведения: перечисление COR_PUB_ENUMPROCESS'
title: Перечисление COR_PUB_ENUMPROCESS
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
ms.openlocfilehash: 66bbd08aabb9d2c93e385ed098bae54754a85b85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801791"
---
# <a name="cor_pub_enumprocess-enumeration"></a>Перечисление COR_PUB_ENUMPROCESS

Идентифицирует тип процесса для перечисления.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a>Члены  
  
|Имя участника|Описание|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|Управляемый процесс.|  
  
## <a name="remarks"></a>Remarks  

 Текущая версия неуправляемого API отладки перечисляет только управляемые процессы.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корпуб. idl, Корпуб. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
