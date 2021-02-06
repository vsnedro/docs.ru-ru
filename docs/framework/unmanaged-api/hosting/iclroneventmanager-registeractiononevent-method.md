---
description: 'Дополнительные сведения о методе: ICLROnEventManager:: Регистерактиононевент'
title: Метод ICLROnEventManager::RegisterActionOnEvent
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: b13209aed6a169185b42c6b9520f21f59f6be3bb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637434"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a>Метод ICLROnEventManager::RegisterActionOnEvent

Регистрирует указатель обратного вызова для указанного события.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `event`  
 окне Одно из значений [еклревент](eclrevent-enumeration.md) , указывающее событие, для которого регистрируется указатель обратного вызова, описанный в `pAction` .  
  
 `pAction`  
 окне Указатель на объект [иактиононклревент](iactiononclrevent-interface.md) , вызываемый при срабатывании зарегистрированного события.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`RegisterActionOnEvent` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  

 Узел может регистрировать обратные вызовы для одного или обоих типов событий, описанных в `EClrEvent` . Узел получает `ICLROnEventManager` интерфейс путем вызова метода [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) .  
  
> [!NOTE]
> События, которые `RegisterActionOnEvent` регистрируются, могут быть запущены более одного раза и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrEvent](eclrevent-enumeration.md)
- [Интерфейс IActionOnCLREvent](iactiononclrevent-interface.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLROnEventManager](iclroneventmanager-interface.md)
