---
title: Метод ICLRTask2::BeginPreventAsyncAbort
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: daf211fcc496f63ef71575abf6a28655004db264
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720247"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>Метод ICLRTask2::BeginPreventAsyncAbort

Откладывает запросы на прерывание нового потока от результирующего прерывания потока в текущем потоке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|HOST_E_INVALIDOPERATION|Метод был вызван в потоке, который не является текущим потоком.|  
  
## <a name="remarks"></a>Комментарии  

 При вызове этого метода значение счетчика "задержка — прерывание потока" для текущего потока увеличивается на единицу.  
  
 Вызовы функций `BeginPreventAsyncAbort` и [ICLRTask2:: EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md) могут быть вложенными. Пока значение счетчика больше нуля, прерывания потока для текущего потока откладываются. Если этот вызов не связан с вызовом `EndPreventAsyncAbort` метода, можно достичь состояния, в котором прерывания потока не могут быть доставлены в текущий поток.  
  
 Задержка не учитывается для потока, который прерывает работу.  
  
 Функциональные возможности, предоставляемые этой функцией, используются внутри виртуальной машины (ВМ). Неправильное использование этих методов может привести к неопределенному поведению в виртуальной машине. Например, при вызове `EndPreventAsyncAbort` без первого вызова `BeginPreventAsyncAbort` значение счетчика может равняться нулю, когда виртуальная машина ранее увеличила ее. Аналогично, внутренний счетчик не проверяется на переполнение. Если он превышает его предельное значение, так как он увеличивается как узлом, так и виртуальной машиной, результирующее поведение не определено.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md)
- [Интерфейс ICLRTask2](iclrtask2-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
