---
title: Метод ICorDebugManagedCallback2::MDANotification
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: f850b3cd35fda8bd554b99e14553100008cb4eca
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208529"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>Метод ICorDebugManagedCallback2::MDANotification
Предоставляет уведомление о том, что при выполнении кода в отлаживаемом приложении обнаружен управляемый помощник по отладке (MDA).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pController`  
 окне Указатель на интерфейс ICorDebugController, предоставляющий процесс или домен приложения, в котором выполнялся MDA.  
  
 Отладчик не должен делать никаких предположений относительно того, является ли контроллер процессом или доменом приложения, хотя он всегда может запрашивать интерфейс для выполнения определения.  
  
 `pThread`  
 окне Указатель на интерфейс ICorDebugThread, предоставляющий управляемый поток, в котором произошло событие отладки.  
  
 Если MDA произошло в неуправляемом потоке, значение `pThread` будет равно null.  
  
 Необходимо получить идентификатор потока операционной системы (ОС) из самого объекта MDA.  
  
 `pMDA`  
 окне Указатель на интерфейс [ICorDebugMDA](icordebugmda-interface.md) , предоставляющий сведения об MDA.  
  
## <a name="remarks"></a>Remarks  
 MDA является эвристическим предупреждением и не требует явных действий отладчика, за исключением вызова [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) для возобновления выполнения отлаживаемого приложения.  
  
 Общеязыковая среда выполнения (CLR) может определять, какие MDA срабатывают и какие данные находятся в любом заданном MDA в любой момент времени. Таким образом, отладчики не должны создавать функции, требующие специальных шаблонов MDA.  
  
 Помощники MDA могут быть поставлены в очередь и срабатывать вскоре после обнаружения помощника по отладке управляемого кода. Это может произойти, если среде выполнения необходимо подождать, пока она достигнет надежной точки для запуска MDA, вместо того, чтобы использовать MDA при обнаружении. Это также означает, что среда выполнения может запустить несколько MDA в одном наборе обратных вызовов в очереди (аналогично операции "присоединение").  
  
 Отладчик должен освободить ссылку на `ICorDebugMDA` экземпляр сразу после возврата из `MDANotification` обратного вызова, чтобы разрешить среде CLR перезапустить память, занятую MDA. Освобождение экземпляра может повысить производительность при срабатывании многих MDA.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Диагностика ошибок посредством управляемых помощников по отладке](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)
- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
