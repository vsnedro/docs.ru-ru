---
description: 'Дополнительные сведения о: интерфейс Икордебужексцептиондебужевент'
title: Интерфейс ICorDebugExceptionDebugEvent
ms.date: 03/30/2017
ms.assetid: f9ba60d8-b54d-417e-bb3e-fde4b41ca44c
ms.openlocfilehash: eacaa344763fb77faef5f66282809d741f017b37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693425"
---
# <a name="icordebugexceptiondebugevent-interface"></a>Интерфейс ICorDebugExceptionDebugEvent

Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetFlags](icordebugexceptiondebugevent-getflags-method.md)|Возвращает флаг, указывающий, может ли исключение быть перехвачено.|  
|[Метод GetNativeIP](icordebugexceptiondebugevent-getnativeip-method.md)|Получает указатель собственного интерфейса для этого события отладки исключения.|  
|[Метод GetStackPointer](icordebugexceptiondebugevent-getstackpointer-method.md)|Получает указатель стека для этого события отладки исключения.|  
  
## <a name="remarks"></a>Remarks  

 Интерфейс `ICorDebugExceptionDebugEvent` реализуется с помощью следующих типов событий:  
  
- [MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)  
  
- [MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)  
  
> [!NOTE]
> Этот интерфейс доступен только в машинном коде .NET. Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
