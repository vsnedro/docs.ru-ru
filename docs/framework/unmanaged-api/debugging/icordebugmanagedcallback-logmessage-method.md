---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback:: LogMessage'
title: Метод ICorDebugManagedCallback::LogMessage
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 199f1f5dca7889a62ef351b4a2731fdb360768d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660522"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a>Метод ICorDebugManagedCallback::LogMessage

Уведомляет отладчик о том, что управляемый поток среды CLR вызвал метод в <xref:System.Diagnostics.EventLog> классе для записи события в журнал.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAppDomain`  
 окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий управляемый поток, который зарегистрировал событие.  
  
 `pThread`  
 окне Указатель на объект ICorDebugThread, представляющий управляемый поток.  
  
 `lLevel`  
 окне Значение перечисления [логгинглевеленум](logginglevelenum-enumeration.md) , указывающее степень серьезности описательного сообщения, записанного в журнал событий.  
  
 `pLogSwitchName`  
 окне Указатель на имя переключателя трассировки.  
  
 `pMessage`  
 окне Указатель на сообщение, записанное в журнал событий.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
