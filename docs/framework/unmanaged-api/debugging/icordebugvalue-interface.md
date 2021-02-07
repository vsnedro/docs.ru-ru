---
description: Дополнительные сведения о интерфейсе ICorDebugValue
title: Интерфейс ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: cae8fdef5c1c49cbabc25d3d547cb5748a9eeee1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690319"
---
# <a name="icordebugvalue-interface"></a>Интерфейс ICorDebugValue

Представляет значение в отлаживаемом процессе. Значением может быть значение Read или Write.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](icordebugvalue-createbreakpoint-method.md)|Этот метод в настоящее время не реализован.|  
|[Метод GetAddress](icordebugvalue-getaddress-method.md)|Возвращает адрес этого `ICorDebugValue` объекта, который находится в процессе отладки.|  
|[Метод GetSize](icordebugvalue-getsize-method.md)|Возвращает размер данного объекта в байтах `ICorDebugValue` .|  
|[Метод GetType](icordebugvalue-gettype-method.md)|Возвращает тип примитива этого `ICorDebugValue` объекта.|  
  
## <a name="remarks"></a>Remarks  

 В общем случае владение объектом значения передается при его возврате. Получатель отвечает за удаление ссылки из объекта после завершения работы с объектом.  
  
 В зависимости от того, откуда было получено значение, оно может остаться недействительным после возобновления процесса. Поэтому в общем случае значение не должно удерживаться в вызове метода [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
