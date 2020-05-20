---
title: Метод ICLRPolicyManager::SetDefaultAction
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetDefaultAction
helpviewer_keywords:
- SetDefaultAction method [.NET Framework hosting]
- ICLRPolicyManager::SetDefaultAction method [.NET Framework hosting]
ms.assetid: f9411e7a-27df-451f-9f6c-d643d6a7a7ce
topic_type:
- apiref
ms.openlocfilehash: c0d8b66c8b85710b0365bfc410188c81431720ff
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703436"
---
# <a name="iclrpolicymanagersetdefaultaction-method"></a>Метод ICLRPolicyManager::SetDefaultAction
Указывает действие политики, которое должна выполнять среда CLR при выполнении указанной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDefaultAction (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `operation`  
 окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее действие, для которого необходимо настроить поведение среды CLR.  
  
 `action`  
 окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие политики, которое должна предпринять среда CLR при `operation` возникновении.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetDefaultAction`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Для `action` задано недопустимое `operation` значение, или для параметра было указано недопустимое `operation` .|  
  
## <a name="remarks"></a>Комментарии  
 Не все значения действий политики могут быть указаны в качестве поведения по умолчанию для операций среды CLR. `SetDefaultAction`обычно может использоваться только для эскалации поведения. Например, узел может указать, что прерывания потока должны быть преобразованы в грубые прерывания потока, но не могут указывать обратно. В следующей таблице описаны допустимые `action` значения для каждого возможного `operation` значения.  
  
|Значение для`operation`|Допустимые значения для`action`|  
|---------------------------|-------------------------------|  
|OPR_ThreadAbort|-Еабортсреад<br />-Ерудеабортсреад<br />-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_ThreadRudeAbortInNonCriticalRegion<br /><br /> OPR_ThreadRudeAbortInCriticalRegion|-Ерудеабортсреад<br />-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_AppDomainUnload|-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_AppDomainRudeUnload|-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_ProcessExit|-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
|OPR_FinalizerRun|-Еноактион<br />-Еабортсреад<br />-Ерудеабортсреад<br />-Еунлоадаппдомаин<br />-Ерудеунлоадаппдомаин<br />-Икситпроцесс<br />-Ефастекситпроцесс<br />-Ерудикситпроцесс<br />-Едисаблерунтиме|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Перечисление EClrOperation](eclroperation-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
