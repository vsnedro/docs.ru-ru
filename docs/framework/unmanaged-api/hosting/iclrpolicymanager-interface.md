---
title: Интерфейс ICLRPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 631301a10aee96bb00aeda6b0b8695f0aea186a8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703478"
---
# <a name="iclrpolicymanager-interface"></a>Интерфейс ICLRPolicyManager
Предоставляет методы, позволяющие основному приложению указывать действия политики, выполняемые в случае сбоев и истечения времени ожидания.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md)|Указывает действие политики, которое должна выполнять среда CLR при возникновении указанного сбоя.|  
|[Метод SetActionOnTimeout](iclrpolicymanager-setactionontimeout-method.md)|Указывает действие политики, которое должна выполнять среда CLR при истечении времени ожидания указанной операции.|  
|[Метод SetDefaultAction](iclrpolicymanager-setdefaultaction-method.md)|Указывает действие политики, которое должна выполнять среда CLR при выполнении указанной операции.|  
|[Метод SetTimeout](iclrpolicymanager-settimeout-method.md)|Задает значение времени ожидания для указанной операции.|  
|[Метод SetTimeoutAndAction](iclrpolicymanager-settimeoutandaction-method.md)|Задает значение времени ожидания для указанной операции и указывает действие политики, которое должна выполнять среда CLR при выполнении операции.|  
|[Метод SetUnhandledExceptionPolicy](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|Задает поведение среды CLR при возникновении необработанного исключения.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Перечисление EClrFailure](eclrfailure-enumeration.md)
- [Перечисление EClrOperation](eclroperation-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
