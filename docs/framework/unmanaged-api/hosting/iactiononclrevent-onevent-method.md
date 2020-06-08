---
title: Метод IActionOnCLREvent::OnEvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent.OnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent::OnEvent
helpviewer_keywords:
- OnEvent method [.NET Framework hosting]
- IActionOnCLREvent::OnEvent method [.NET Framework hosting]
ms.assetid: 0970f10c-4304-4c12-91c0-83e51455afb4
topic_type:
- apiref
ms.openlocfilehash: bbf5e299285071ba6d43fd2c40fc724d19bc7b2a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504359"
---
# <a name="iactiononclreventonevent-method"></a>Метод IActionOnCLREvent::OnEvent
Выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](iclroneventmanager-registeractiononevent-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnEvent (  
    [in] EClrEvent event,  
    [in] PVOID     data  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `event`  
 окне Одно из значений [еклревент](eclrevent-enumeration.md) , указывающее тип события.  
  
 `data`  
 окне Указатель на объект, содержащий сведения о `event` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`OnEvent`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Если метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы метода размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `data`Параметр является указателем на объект неопределенного типа. Если `event` параметр имеет значение `Event_DomainUnload` , то `data` является числовым идентификатором для <xref:System.AppDomain> выгрузки. Узел может предпринять соответствующие действия, используя этот идентификатор в качестве ключа.  
  
 Если `event` имеет значение `Event_MDAFired` , `data` то является указателем на экземпляр [мдаинфо](mdainfo-structure.md) , который содержит выходные данные сообщения от помощника по отладке управляемого кода (MDA). MDA — это функция среды CLR, которая помогает разработчикам выполнять отладку путем создания сообщений XML о событиях, которые в противном случае сложны для перехвата. Такие сообщения могут быть особенно полезны при отладке переходов между управляемым и неуправляемым кодом. Дополнительные сведения см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Диагностика ошибок посредством управляемых помощников по отладке](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Перечисление EClrEvent](eclrevent-enumeration.md)
- [Интерфейс IActionOnCLREvent](iactiononclrevent-interface.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLROnEventManager](iclroneventmanager-interface.md)
- [Структура MDAInfo](mdainfo-structure.md)
