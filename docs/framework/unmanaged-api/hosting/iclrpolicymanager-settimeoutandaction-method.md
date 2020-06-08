---
title: Метод ICLRPolicyManager::SetTimeoutAndAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetTimeoutAndAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetTimeoutAndAction
helpviewer_keywords:
- ICLRPolicyManager::SetTimeoutAndAction method [.NET Framework hosting]
- SetTimeoutAndAction method [.NET Framework hosting]
ms.assetid: 60454f91-d855-4ddf-bb6d-60a02f5eabab
topic_type:
- apiref
ms.openlocfilehash: 02e836601be72d54f561e077cd3c466470bafb25
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504099"
---
# <a name="iclrpolicymanagersettimeoutandaction-method"></a>Метод ICLRPolicyManager::SetTimeoutAndAction
Задает значение времени ожидания для указанной операции и указывает действие политики, которое должна выполнять среда CLR при выполнении операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetTimeoutAndAction (  
    [in] EClrOperation operation,  
    [in] DWORD dwMilliseconds,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `operation`  
 окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее операцию, для которой необходимо задать время ожидания и политику `action` . Поддерживаются следующие значения.  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `dwMilliseconds`  
 окне Новое значение времени ожидания в миллисекундах. Значение бесконечности приводит к тому, что `operation` время ожидания никогда не истекает.  
  
 `action`  
 окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие политики, ВЫПОЛНЯЕМое средой CLR при `operation` возникновении.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetTimeoutAndAction`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Не удается задать время ожидания для указанного `operation` или указано недопустимое значение для `action` .|  
  
## <a name="remarks"></a>Примечания  
 `SetTimeoutAndAction`Инкапсулирует возможности методов [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) и [ICLRPolicyManager:: сетактиононтимеаут](iclrpolicymanager-setactionontimeout-method.md) , и их можно вызывать вместо последовательных вызовов этих двух методов.  
  
> [!IMPORTANT]
> Не все значения действий политики могут быть указаны в качестве поведения времени ожидания для операций среды CLR. Допустимые значения см. в подразделах "Примечания" для этих двух методов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrOperation](eclroperation-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Метод SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)
- [ICLRPolicyManager:: SetTimeoutAndAction](iclrpolicymanager-settimeoutandaction-method.md)
