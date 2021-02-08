---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback2:: Ексцептионунвинд'
title: Метод ICorDebugManagedCallback2::ExceptionUnwind
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.ExceptionUnwind
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind
helpviewer_keywords:
- ICorDebugManagedCallback2::ExceptionUnwind method [.NET Framework debugging]
- ExceptionUnwind method [.NET Framework debugging]
ms.assetid: aaf5938d-179c-4eaa-8d35-8523a4fadded
topic_type:
- apiref
ms.openlocfilehash: 2d98fb21cdbb0db25a11761ac9b00e99e1526cc0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790854"
---
# <a name="icordebugmanagedcallback2exceptionunwind-method"></a>Метод ICorDebugManagedCallback2::ExceptionUnwind

Предоставляет уведомление о состоянии во время процесса очистки исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT ExceptionUnwind (  
    [in] ICorDebugAppDomain                  *pAppDomain,  
    [in] ICorDebugThread                     *pThread,  
    [in] CorDebugExceptionUnwindCallbackType  dwEventType,  
    [in] DWORD                                dwFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий поток, в котором было создано исключение.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий поток, в котором было создано исключение.  
  
 `dwEventType`  
 окне Значение перечисления Кордебужексцептионунвиндкаллбакктипе, указывающее событие, сигнальное функцией обратного вызова на этапе очистки.  
  
 `dwFlags`  
 окне Значение перечисления [кордебужексцептионфлагс](cordebugexceptionflags-enumeration.md) , которое указывает дополнительные сведения об исключении.  
  
## <a name="remarks"></a>Remarks  

 `ExceptionUnwind` вызывается в различных точках на этапе очистки процесса обработки исключений. `ExceptionUnwind` может вызываться более одного раза при очистке одного исключения.  
  
 Если `dwEventType` = DEBUG_EXCEPTION_INTERCEPTED, указатель инструкции будет находиться в конечном кадре потока в точке следования до (это может быть несколько инструкций до) инструкции, вызвавшей исключение.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
