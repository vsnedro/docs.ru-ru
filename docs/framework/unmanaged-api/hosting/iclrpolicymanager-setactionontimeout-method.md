---
title: Метод ICLRPolicyManager::SetActionOnTimeout
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
ms.openlocfilehash: 0b8e7dfbe377e60b548003af10fb11392b514030
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703454"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a>Метод ICLRPolicyManager::SetActionOnTimeout
Указывает действие политики, которое должна выполнять среда CLR при истечении времени ожидания указанной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `operation`  
 окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее операцию, для которой необходимо указать действие времени ожидания. Поддерживаются следующие значения.  
  
- OPR_AppDomainUnload  
  
- OPR_ProcessExit  
  
- OPR_ThreadRudeAbortInCriticalRegion  
  
- OPR_ThreadRudeAbortInNonCriticalRegion  
  
 `action`  
 окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие политики, выполняемое при истечении времени ожидания операции.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetActionOnTimeout`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Не удается задать время ожидания для указанного `operation` или указано недопустимое значение для `operation` .|  
  
## <a name="remarks"></a>Комментарии  
 Значение времени ожидания может быть либо временем ожидания по умолчанию, установленным средой CLR, либо значением, заданным узлом при вызове метода [ICLRPolicyManager:: setTimeout](iclrpolicymanager-settimeout-method.md) .  
  
 Не все значения действий политики могут быть указаны в качестве поведения времени ожидания для операций среды CLR. `SetActionOnTimeout`обычно используется только для эскалации поведения. Например, узел может указать, что прерывания потока должны быть преобразованы в грубые прерывания потока, но не могут указывать обратно. В следующей таблице описаны допустимые `action` значения для допустимых `operation` значений.  
  
|Значение для`operation`|Допустимые значения для`action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-Ерудеабортсреад<br />-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_AppDomainUnload|-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_ProcessExit|-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Перечисление EClrOperation](eclroperation-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
