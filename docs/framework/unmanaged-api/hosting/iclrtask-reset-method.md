---
title: Метод ICLRTask::Reset
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
ms.openlocfilehash: b87bc026a2cac2d0b913128c43142d56aee03025
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725200"
---
# <a name="iclrtaskreset-method"></a>Метод ICLRTask::Reset

Информирует среду CLR о том, что узел завершил задачу, и позволяет среде CLR повторно использовать текущий экземпляр [ICLRTask](iclrtask-interface.md) для представления другой задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `fFull`  
 [in] `true` , если среда выполнения должна сбрасывать все статические значения, связанные с потоками, в дополнение к сведениям о безопасности и национальной настройке, связанным с текущим `ICLRTask` экземпляром; в противном случае — значение `false` .  
  
 Если значение равно `true` , среда выполнения сбрасывает данные, сохраненные с помощью <xref:System.Threading.Thread.AllocateDataSlot%2A> или <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`Reset` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или обработать вызов. успешность|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR может перезапустить ранее созданные `ICLRTask` экземпляры, чтобы избежать лишних затрат на создание новых экземпляров каждый раз, когда требуется новая задача. Узел включает эту функцию, вызывая `ICLRTask::Reset` вместо [ICLRTask:: ExitTask](iclrtask-exittask-method.md) после завершения задачи. В следующем списке приведено краткое описание обычного жизненного цикла `ICLRTask` экземпляра.  
  
1. Среда выполнения создает новый `ICLRTask` экземпляр.  
  
2. Среда выполнения вызывает [IHostTaskManager:: GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md) , чтобы получить ссылку на текущую задачу узла.  
  
3. Среда выполнения вызывает метод [IHostTask:: SetCLRTask](ihosttask-setclrtask-method.md) , чтобы связать новый экземпляр с задачей хоста.  
  
4. Задача выполняется и завершается.  
  
5. Узел уничтожает задачу путем вызова `ICLRTask::ExitTask` .  
  
 `Reset` изменяет этот сценарий двумя способами. На шаге 5, приведенном выше, вызывается вызов узла `Reset` для сброса задачи до чистого состояния, а затем отделяет `ICLRTask` экземпляр от связанного экземпляра [IHostTask](ihosttask-interface.md) . При необходимости узел также может кэшировать `IHostTask` экземпляр для повторного использования. На шаге 1 выше среда выполнения извлекает `ICLRTask` из кэша, а не создает новый экземпляр.  
  
 Этот подход хорошо работает, когда узел также имеет пул рабочих задач с многократным использованием. Когда узел уничтожает один из его `IHostTask` экземпляров, он уничтожает соответствующий `ICLRTask` вызовом `ExitTask` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
