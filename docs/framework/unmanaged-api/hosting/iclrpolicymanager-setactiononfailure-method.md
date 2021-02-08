---
description: 'Дополнительные сведения о методе: ICLRPolicyManager:: Сетактиононфаилуре'
title: Метод ICLRPolicyManager::SetActionOnFailure
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnFailure
helpviewer_keywords:
- SetActionOnFailure method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnFailure method [.NET Framework hosting]
ms.assetid: 4664033f-db97-4388-b988-2ec470796e58
topic_type:
- apiref
ms.openlocfilehash: 67d3ca5d7924caf0a768b4de53b4b24f1c72fa27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789805"
---
# <a name="iclrpolicymanagersetactiononfailure-method"></a>Метод ICLRPolicyManager::SetActionOnFailure

Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetActionOnFailure (  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `failure`  
 окне Одно из значений [еклрфаилуре](eclrfailure-enumeration.md) , указывающее тип сбоя, для которого необходимо выполнить действие.  
  
 `action`  
 окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие, выполняемое в случае сбоя. Список поддерживаемых значений см. в разделе "Примечания".  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`SetActionOnFailure` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. После того как метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|Действие политики не может быть задано для указанной операции, или для операции указано недопустимое действие политики.|  
  
## <a name="remarks"></a>Remarks  

 По умолчанию среда CLR создает исключение, когда не удается выделить ресурс, например память. `SetActionOnFailure` позволяет узлу переопределить это поведение, указав действие политики для выполнения при сбое. В следующей таблице показаны поддерживаемые сочетания значений [еклрфаилуре](eclrfailure-enumeration.md) и [еполициактион](epolicyaction-enumeration.md) . (Префикс FAIL_ опущен из значений [еклрфаилуре](eclrfailure-enumeration.md) .)  
  
||нонкритикалресаурце|критикалресаурце|фаталрунтиме|орфанедлокк|StackOverflow|AccessViolationException|кодеконтракт|  
|-|-------------------------|----------------------|------------------|------------------|-------------------|---------------------|------------------|  
|`eNoAction`|X|X||||н/д||  
|есровексцептион|X|X||||н/д||  
|`eAbortThread`|X|X||||н/д|X|  
|`eRudeAbortThread`|X|X||||н/д|X|  
|`eUnloadAppDomain`|X|X||X||н/д|X|  
|`eRudeUnloadAppDomain`|X|X||X|X|н/д|X|  
|`eExitProcess`|X|X||X|X|н/д|X|  
|ефастекситпроцесс|X|X||X|X|н/д||  
|`eRudeExitProcess`|X|X|X|X|X|н/д||  
|`eDisableRuntime`|X|X|X|X|X|н/д||  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](eclrfailure-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
