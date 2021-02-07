---
description: 'Дополнительные сведения о: интерфейс ICorDebugValue2'
title: Интерфейс ICorDebugValue2
ms.date: 03/30/2017
api_name:
- ICorDebugValue2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2
helpviewer_keywords:
- ICorDebugValue2 interface [.NET Framework debugging]
ms.assetid: 3ff2ad2a-da5a-461b-8627-1a8eba49df9c
topic_type:
- apiref
ms.openlocfilehash: b408bb5d1732a60fc9aa8ffb93321d3542f2cab7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690266"
---
# <a name="icordebugvalue2-interface"></a>Интерфейс ICorDebugValue2

Расширяет интерфейс "ICorDebugValue" для обеспечения поддержки объектов "ICorDebugType".  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetExactType](icordebugvalue2-getexacttype-method.md)|Возвращает указатель интерфейса на `ICorDebugType` объект, представляющий <xref:System.Type> это значение.|  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)

- [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)
