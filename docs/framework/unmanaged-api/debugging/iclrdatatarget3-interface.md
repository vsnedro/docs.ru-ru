---
description: 'Дополнительные сведения о: интерфейс метод iclrdatatarget3'
title: Интерфейс ICLRDataTarget3
ms.date: 03/30/2017
api_name:
- ICLRDataTarget3
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: d2711bdf-64b3-404c-a0c3-01ba4907f703
topic_type:
- apiref
ms.openlocfilehash: deea609298563e60897f9bedab9fb1e175dc7b73
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794793"
---
# <a name="iclrdatatarget3-interface"></a>Интерфейс ICLRDataTarget3

Подкласс [ICLRDataTarget2](iclrdatatarget2-interface.md) , предоставляющий доступ к сведениям об исключениях.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetExceptionRecord](iclrdatatarget3-getexceptionrecord-method.md)|Вызывается службами доступа к данным среды CLR для извлечения записи исключения, связанной с целевым процессом.|  
|[Метод GetExceptionContextRecord](iclrdatatarget3-getexceptioncontextrecord-method.md)|Вызывается службами доступа к данным среды CLR для извлечения записи контекста, связанной с целевым процессом.|  
|[Метод GetExceptionThreadID](iclrdatatarget3-getexceptionthreadid-method.md)|Вызывается службами доступа к данным среды CLR для получения идентификатора потока, вызвавшего исключение.|  
  
## <a name="remarks"></a>Remarks  

 Клиент API (то есть отладчик) должен реализовывать этот интерфейс для определенного целевого процесса по мере необходимости. Например, реализация активного процесса будет отличаться от реализации дампа памяти. Целевой объект может не поддерживать изменение областей его памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[v451_update](../../../../includes/net-current-v451-nov-plus.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)
- [Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
