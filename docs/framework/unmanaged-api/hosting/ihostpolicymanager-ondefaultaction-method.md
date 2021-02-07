---
description: 'Дополнительные сведения о методе: IHostPolicyManager:: OnDefaultAction'
title: Метод IHostPolicyManager::OnDefaultAction
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnDefaultAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnDefaultAction
helpviewer_keywords:
- OnDefaultAction method [.NET Framework hosting]
- IHostPolicyManager::OnDefaultAction method [.NET Framework hosting]
ms.assetid: 071e73bd-4795-470f-9373-cfaef553b7f2
topic_type:
- apiref
ms.openlocfilehash: ea474734f7bc0a5210c5aecf605452909b261a87
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671929"
---
# <a name="ihostpolicymanagerondefaultaction-method"></a>Метод IHostPolicyManager::OnDefaultAction

Уведомляет основное приложение о том, что среда CLR собирается выполнить действие по умолчанию, заданное вызовом метода [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) в ответ на прерывание или <xref:System.AppDomain> выгрузку потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT OnDefaultAction (  
    [in] EClrOperation  operation,
    [in] EPolicyAction  action  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `operation`  
 окне Одно из значений [еклроператион](eclroperation-enumeration.md) , указывающее тип события, на которое отвечает среда CLR.  
  
 `action`  
 окне Одно из значений [еполициактион](epolicyaction-enumeration.md) , указывающее действие, которое среда CLR принимает в ответ на событие.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|`OnDefaultAction` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или обработать вызов. успешность|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrOperation](eclroperation-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Интерфейс IHostPolicyManager](ihostpolicymanager-interface.md)
