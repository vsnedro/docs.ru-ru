---
description: 'Дополнительные сведения о: интерфейс ICorDebugThread4'
title: Интерфейс ICorDebugThread4
ms.date: 03/30/2017
api_name:
- ICorDebugThread4
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4
helpviewer_keywords:
- ICorDebugThread4 interface [.NET Framework debugging]
ms.assetid: a8c7719a-322b-4133-8566-4c27218dc104
topic_type:
- apiref
ms.openlocfilehash: 4ad587cee81ce635df0a8917b7a6d68e60aaf0b3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800920"
---
# <a name="icordebugthread4-interface"></a>Интерфейс ICorDebugThread4

Предоставляет сведения о блокировке потока.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBlockingObjects](icordebugthread4-getblockingobjects-method.md)|Предоставляет упорядоченное перечисление структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) , которые предоставляют сведения о блокировке потока.|  
|[Метод HadUnhandledException](icordebugthread4-hadunhandledexception-method.md)|Указывает, имел ли когда-либо поток необработанное исключение.|  
|[Метод GetCurrentCustomDebuggerNotification](icordebugthread4-getcurrentcustomdebuggernotification-method.md)|Возвращает текущий объект [ICorDebugManagedCallback3:: CustomNotification](icordebugmanagedcallback3-customnotification-method.md) в текущем потоке.|  
  
## <a name="remarks"></a>Remarks  

 Этот интерфейс является логическим расширением интерфейсов ICorDebugThread, ICorDebugThread2 и [ICorDebugThread3](icordebugthread3-interface.md) .  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
