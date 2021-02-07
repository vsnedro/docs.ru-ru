---
description: Дополнительные сведения о перечислении Кордебугсреадстате
title: Перечисление CorDebugThreadState
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 0cf83ee31547e49ccc7d09e0ab4ee85548688b36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661812"
---
# <a name="cordebugthreadstate-enumeration"></a>Перечисление CorDebugThreadState

Указывает состояние потока для отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`THREAD_RUN`|Поток выполняется свободно, если не происходит событие отладки.|  
|`THREAD_SUSPEND`|Поток не может быть запущен.|  
  
## <a name="remarks"></a>Remarks  

 Отладчик использует `CorDebugThreadState` перечисление для управления выполнением потока. Состояние потока можно задать с помощью метода [ICorDebugThread:: SetDebugState](icordebugthread-setdebugstate-method.md) или [ICorDebugController:: SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md) .  
  
 Обратный вызов, предоставленный [API размещения](../hosting/index.md) , позволяет передавать сообщения, поэтому прерывание состояния не требуется.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](debugging-enumerations.md)
