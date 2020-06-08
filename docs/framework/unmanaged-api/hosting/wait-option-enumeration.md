---
title: Перечисление WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
ms.openlocfilehash: 2f83bc5b114b746958f936c311efa823d88441d1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503891"
---
# <a name="wait_option-enumeration"></a>Перечисление WAIT_OPTION
Содержит значения, указывающие действие, которое должен выполнить узел при выполнении операции, запрашиваемой блоками среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Уведомляет узел о том, что задача должна быть пробуждена, если среда CLR вызывает метод [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|`WAIT_MSGPUMP`|Уведомляет узел о том, что он должен передавать сообщения в текущем потоке операционной системы, если поток блокируется. Среда выполнения задает это значение только в <xref:System.Threading.ApartmentState.STA> потоке.|  
|`WAIT_NOTINDEADLOCK`|Сообщает узлу, что указанный запрос на синхронизацию не может быть разбит узлом. Это значит, что узел не может вернуть `HOST_E_DEADLOCK` .|  
  
## <a name="remarks"></a>Примечания  
 Методы [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) и [IHostTaskManager:: свитчтотаск](ihosttaskmanager-switchtotask-method.md) принимают параметр этого типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](hosting-enumerations.md)
