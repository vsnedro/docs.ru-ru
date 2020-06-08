---
title: Метод IHostTaskManager::LeaveRuntime
ms.date: 03/30/2017
api_name:
- IHostTaskManager.LeaveRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::LeaveRuntime
helpviewer_keywords:
- IHostTaskManager::LeaveRuntime method [.NET Framework hosting]
- LeaveRuntime method [.NET Framework hosting]
ms.assetid: 43689cc4-e48e-46e5-a22d-bafd768b8759
topic_type:
- apiref
ms.openlocfilehash: deaebbce3b9b8a26bf9668b826a6818dba94dcc3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501385"
---
# <a name="ihosttaskmanagerleaveruntime-method"></a>Метод IHostTaskManager::LeaveRuntime
Уведомляет основное приложение о том, что Текущая выполняемая задача собирается покинуть среду CLR, и введите неуправляемый код.  
  
> [!IMPORTANT]
> Соответствующий вызов [IHostTaskManager:: EnterRuntime](ihosttaskmanager-enterruntime-method.md) уведомляет основное приложение о том, что выполняемая в данный момент задача повторно вводит управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LeaveRuntime (  
    [in] SIZE_T target  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `target`  
 окне Адрес в сопоставленном переносимом исполняемом файле неуправляемой функции для вызова.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`LeaveRuntime`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для завершения запрошенного выделения.|  
  
## <a name="remarks"></a>Примечания  
 Последовательности вызовов для и из неуправляемого кода могут быть вложенными. Например, приведенный ниже список описывает гипотетическую ситуацию, в которой последовательность вызовов `LeaveRuntime` , [IHostTaskManager:: реверсинтеррунтиме](ihosttaskmanager-reverseenterruntime-method.md), [IHostTaskManager:: ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md), и узел, `IHostTaskManager::EnterRuntime` позволяющий находить вложенные слои.  
  
|Действие|Вызов соответствующего метода|  
|------------|-------------------------------|  
|Управляемый исполняемый файл Visual Basic вызывает неуправляемую функцию, написанную на языке C, с помощью вызова неуправляемого кода.|`IHostTaskManager::LeaveRuntime`|  
|Неуправляемая функция C вызывает метод в управляемой библиотеке DLL, написанной на языке C#.|`IHostTaskManager::ReverseEnterRuntime`|  
|Управляемая функция C# вызывает другую неуправляемую функцию, написанную на языке C, также используя вызов неуправляемого кода.|`IHostTaskManager::LeaveRuntime`|  
|Вторая неуправляемая функция возвращает выполнение функции C#.|`IHostTaskManager::EnterRuntime`|  
|Функция C# возвращает выполнение в первую неуправляемую функцию.|`IHostTaskManager::ReverseLeaveRuntime`|  
|Первая неуправляемая функция возвращает выполнение в программу Visual Basic.|`IHostTaskManager::EnterRuntime`|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](ihosttask-interface.md)
- [Интерфейс IHostTaskManager](ihosttaskmanager-interface.md)
