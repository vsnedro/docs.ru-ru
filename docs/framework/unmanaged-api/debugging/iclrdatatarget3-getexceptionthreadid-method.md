---
title: Метод ICLRDataTarget3::GetExceptionThreadID
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetExceptionThreadID
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 307d6ac7-4a86-45f3-999d-6b47004a68f2
topic_type:
- apiref
ms.openlocfilehash: 0a8b7a90cd909379f870f6a501a940386d2e1451
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723601"
---
# <a name="iclrdatatarget3getexceptionthreadid-method"></a>Метод ICLRDataTarget3::GetExceptionThreadID

Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExceptionThreadID(  
    [out] ULONG32* threadID  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `threadID`  
 [из] Идентификатор потока, вызвавшего исключение.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. Коды `HRESULT` могут включать значения, приведенные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Не удалось найти допустимый идентификатор потока для исключения.|  
  
## <a name="remarks"></a>Комментарии  

 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget3](iclrdatatarget3-interface.md)
- [Метод GetExceptionContextRecord](iclrdatatarget3-getexceptioncontextrecord-method.md)
- [Метод GetExceptionRecord](iclrdatatarget3-getexceptionrecord-method.md)
