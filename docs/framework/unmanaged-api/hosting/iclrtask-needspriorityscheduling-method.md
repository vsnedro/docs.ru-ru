---
description: 'Дополнительные сведения о методе ICLRTask:: Нидсприоритисчедулинг'
title: Метод ICLRTask::NeedsPriorityScheduling
ms.date: 03/30/2017
api_name:
- ICLRTask.NeedsPriorityScheduling
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::NeedsPriorityScheduling
helpviewer_keywords:
- ICLRTask::NeedsPriorityScheduling method [.NET Framework hosting]
- NeedsPriorityScheduling method [.NET Framework hosting]
ms.assetid: 9c9db3f3-26bf-4317-88de-5eb926a22a1d
topic_type:
- apiref
ms.openlocfilehash: e6e1b93b38d86259dc2f405f8512ec1063fe7b3b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781770"
---
# <a name="iclrtaskneedspriorityscheduling-method"></a>Метод ICLRTask::NeedsPriorityScheduling

Возвращает значение, указывающее, нужно ли пометить текущую задачу, для которой выполняется переключение, в качестве высокого приоритета для повторного планирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NeedsPriorityScheduling (  
    [out] BOOL *pbNeedsPriorityScheduling  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbNeedsPriorityRescheduling`  
 [out] `true` , если узел должен попытаться повторно запланировать текущий экземпляр задачи как можно скорее. в противном случае — значение `false` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`NeedsPriorityRescheduling` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 В ситуациях, когда задача находится в близком к сбору сборщиком мусора, среда CLR устанавливает значение `pbNeedsPriorityScheduling` равным `true` , что указывает на перепланирование с высоким приоритетом. Это позволяет основному приложению быстро планировать задачу, уменьшая вероятность задержек при сборке мусора и позволяя основному приложению и среде выполнения взаимодействовать для экономии ресурсов памяти.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
