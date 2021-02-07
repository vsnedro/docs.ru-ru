---
description: 'Дополнительные сведения: перечисление WAIT_OPTION'
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
ms.openlocfilehash: 1d651909e0f62f2db7478a6e0b37139d1f953196
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679138"
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Уведомляет узел о том, что задача должна быть пробуждена, если среда CLR вызывает метод [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|`WAIT_MSGPUMP`|Уведомляет узел о том, что он должен передавать сообщения в текущем потоке операционной системы, если поток блокируется. Среда выполнения задает это значение только в <xref:System.Threading.ApartmentState.STA> потоке.|  
|`WAIT_NOTINDEADLOCK`|Сообщает узлу, что указанный запрос на синхронизацию не может быть разбит узлом. Это значит, что узел не может вернуть `HOST_E_DEADLOCK` .|  
  
## <a name="remarks"></a>Remarks  

 Методы [IHostTaskManager:: Sleep](ihosttaskmanager-sleep-method.md) и [IHostTaskManager:: свитчтотаск](ihosttaskmanager-switchtotask-method.md) принимают параметр этого типа.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](hosting-enumerations.md)
