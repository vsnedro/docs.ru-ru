---
title: Метод ICLRDebugManager::EndConnection
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.EndConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::EndConnection
helpviewer_keywords:
- ICLRDebugManager::EndConnection method [.NET Framework hosting]
- EndConnection method [.NET Framework hosting]
ms.assetid: 89dc7363-2f29-4eb2-8f23-fccdda6a76a6
topic_type:
- apiref
ms.openlocfilehash: d3d081e389e29833f24063ba75289f3db8c5504a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504281"
---
# <a name="iclrdebugmanagerendconnection-method"></a>Метод ICLRDebugManager::EndConnection
Удаляет связь между списком задач и идентификатором и понятным именем.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EndConnection (  
    [in] CONNID dwConnectionId  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwConnectionId`  
 окне Специфический для узла идентификатор соединения и связанный список задач среды CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`EndConnection`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|[Бегинконнектион](iclrdebugmanager-beginconnection-method.md) никогда не вызывался с помощью `dwConnectionId` , или `dwConnectionId` равен нулю.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRDebugManager](iclrdebugmanager-interface.md) предоставляет три метода, `BeginConnection` , [SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)и `EndConnection` , для связывания списков задач с идентификаторами и понятными именами.  
  
> [!IMPORTANT]
> Эти три метода должны вызываться в определенном порядке для каждого набора задач. `BeginConnection`вызывается первым для установления нового соединения. `SetConnectionTasks`вызывается далее для предоставления набора задач, которые должны быть связаны с этим соединением. `EndConnection`вызывается последним, чтобы удалить связь между списком задач и идентификатором и понятным именем. Однако вызовы для различных соединений могут быть вложенными.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRDebugManager](iclrdebugmanager-interface.md)
- [Метод BeginConnection](iclrdebugmanager-beginconnection-method.md)
- [Метод SetConnectionTasks](iclrdebugmanager-setconnectiontasks-method.md)
- [Интерфейс IHostControl](ihostcontrol-interface.md)
