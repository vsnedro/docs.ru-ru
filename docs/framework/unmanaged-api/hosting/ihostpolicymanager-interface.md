---
title: Интерфейс IHostPolicyManager
ms.date: 03/30/2017
api_name:
- IHostPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager
helpviewer_keywords:
- IHostPolicyManager interface [.NET Framework hosting]
ms.assetid: 8c4aa124-5e00-46d9-b1e8-57ba6574bb0d
topic_type:
- apiref
ms.openlocfilehash: 3c85bcbe8aee453b19217ebd1f48feea113e3bb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731225"
---
# <a name="ihostpolicymanager-interface"></a>Интерфейс IHostPolicyManager

Предоставляет методы, уведомляющие узел о действиях, выполняемых средой CLR в случае прерываний, времени ожидания или сбоев.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод OnDefaultAction](ihostpolicymanager-ondefaultaction-method.md)|Уведомляет основное приложение о том, что среда CLR собирается принять действие по умолчанию, заданное вызовом метода [ICLRPolicyManager:: SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md) в ответ на прерывание или <xref:System.AppDomain> выгрузку потока.|  
|[Метод OnFailure](ihostpolicymanager-onfailure-method.md)|Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом [ICLRPolicyManager:: сетактиононфаилуре](iclrpolicymanager-setactiononfailure-method.md) в ответ на выделение ресурсов или сбой при реорганизации.|  
|[Метод OnTimeout](ihostpolicymanager-ontimeout-method.md)|Уведомляет основное приложение о том, что среда CLR собирается выполнить действие, заданное вызовом метода [ICLRPolicyManager:: сетактиононтимеаут](iclrpolicymanager-setactionontimeout-method.md) в ответ на время ожидания.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисление EClrFailure](eclrfailure-enumeration.md)
- [Перечисление EClrOperation](eclroperation-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
