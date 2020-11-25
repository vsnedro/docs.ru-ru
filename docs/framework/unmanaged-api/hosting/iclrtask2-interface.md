---
title: Интерфейс ICLRTask2
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: 9332b3462ba389783a113d173e32850d40427ce2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720234"
---
# <a name="iclrtask2-interface"></a>Интерфейс ICLRTask2

Предоставляет все функциональные возможности интерфейса [ICLRTask](iclrtask-interface.md) ; Кроме того, предоставляет методы, которые позволяют задерживать прерывания потока в текущем потоке.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md)|Откладывает запросы на прерывание нового потока в текущем потоке.|  
|[Метод EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md)|Разрешает новые или ожидающие запросы на прерывание потока в результате прерывания потока в текущем потоке.|  
  
## <a name="remarks"></a>Комментарии  

 `ICLRTask2`Интерфейс наследует `ICLRTask` интерфейс и добавляет методы, позволяющие узлу откладывать прерывания потока, чтобы защитить область кода, которая не должна завершаться ошибкой. Вызов `BeginPreventAsyncAbort` увеличивает счетчик прерывания задержки потока для текущего потока и вызывает метод `EndPreventAsyncAbort` декремента. Вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` могут быть вложенными. Пока значение счетчика больше нуля, прерывания потока для текущего потока откладываются.  
  
 Если вызовы `BeginPreventAsyncAbort` и `EndPreventAsyncAbort` не являются парными, то можно достичь состояния, в котором прерывания потока не могут быть доставлены в текущий поток.  
  
 Задержка не учитывается для потока, который прерывает работу.  
  
 Функциональные возможности, предоставляемые этой функцией, используются внутри виртуальной машины (ВМ). Неправильное использование этих методов может привести к неопределенному поведению в виртуальной машине. Например, при вызове `EndPreventAsyncAbort` без первого вызова `BeginPreventAsyncAbort` значение счетчика может равняться нулю, когда виртуальная машина ранее увеличила ее. Аналогично, внутренний счетчик не проверяется на переполнение. Если он превышает его предельное значение, так как он увеличивается как узлом, так и виртуальной машиной, результирующее поведение не определено.  
  
 Сведения о членах, унаследованных от `ICLRTask` и о других применениях этого интерфейса, см. в разделе интерфейс [ICLRTask](iclrtask-interface.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
