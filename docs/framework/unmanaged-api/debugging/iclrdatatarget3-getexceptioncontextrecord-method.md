---
title: Метод ICLRDataTarget3::GetExceptionContextRecord
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICLRDataTarget3.GetContextRecord
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 66076ed5-f05c-4114-9788-94cb143abb8a
topic_type:
- apiref
ms.openlocfilehash: 3e73d0fc48dcfeafb3fe2f23ec07cdc04a561a9e
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860447"
---
# <a name="iclrdatatarget3getexceptioncontextrecord-method"></a>Метод ICLRDataTarget3::GetExceptionContextRecord
Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом. Например, для целевого объекта дампа это будет эквивалентно записи контекста, передаваемой через `ExceptionParam` аргумент в функцию [Минидумпвритедумп](/windows/desktop/api/minidumpapiset/nf-minidumpapiset-minidumpwritedump) в библиотеке справки по отладке Windows (DBGHELP).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExceptionContextRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize)] BYTE* buffer  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bufferSize`  
 [в] Размер входного буфера в байтах. Он должен быть достаточно большим, чтобы вместить запись контекста.  
  
 `bufferUsed`  
 [из] Указатель на тип `ULONG32`, который получает количество байтов, фактически записанных в буфер.  
  
 `buffer`  
 [из] Указатель на буфер памяти, который получает копию записи контекста. Запись исключения возвращается как тип [контекста](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращается значение `S_OK` при успешном выполнении или код ошибки `HRESULT` при сбое. Коды `HRESULT` могут включать значения, приведенные в следующей таблице.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|`S_OK`|Метод успешно выполнен. Запись контекста скопирована в буфер вывода.|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|Нет записей контекста, связанных с целевым объектом.|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|Размер входного буфера недостаточен для сохранения записи контекста.|  
  
## <a name="remarks"></a>Примечания  
 [Контекст](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) — это зависящая от платформы структура, определенная в заголовках, предоставляемых Windows SDK.  
  
 Этот метод реализуется модулем записи отладчика.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataTarget3](iclrdatatarget3-interface.md)
- [Метод GetExceptionRecord](iclrdatatarget3-getexceptionrecord-method.md)
- [Метод GetExceptionThreadID](iclrdatatarget3-getexceptionthreadid-method.md)
