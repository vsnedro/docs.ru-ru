---
title: Метод ICorDebugMDA::GetOSThreadId
ms.date: 03/30/2017
api_name:
- ICorDebugMDA.GetOSThreadId
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMDA::GetOSThreadId
helpviewer_keywords:
- ICorDebugMDA::GetOSThreadId method [.NET Framework debugging]
- GetOSThreadId method [.NET Framework debugging]
ms.assetid: 7ca7c364-ade4-4219-b434-9f6ae2359be6
topic_type:
- apiref
ms.openlocfilehash: 80248bba6d11b8af07aa0517cb41c8a4f783b5e0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710900"
---
# <a name="icordebugmdagetosthreadid-method"></a>Метод ICorDebugMDA::GetOSThreadId

Возвращает идентификатор потока операционной системы (ОС), по которому выполняется управляемый помощник по отладке (MDA), представленный [ICorDebugMDA](icordebugmda-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetOSThreadId (  
    [out] DWORD    *pOsTid  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pOsTid`  
 заполняет Указатель на идентификатор потока операционной системы.  
  
## <a name="remarks"></a>Комментарии  

 Поток операционной системы используется вместо ICorDebugThread, чтобы разрешить ситуации, в которых MDA срабатывает либо в собственном потоке, либо в управляемом потоке, который еще не вошел в управляемый код.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugMDA](icordebugmda-interface.md)
- [Диагностика ошибок посредством управляемых помощников по отладке](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
