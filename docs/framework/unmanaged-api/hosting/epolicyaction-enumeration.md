---
title: Перечисление EPolicyAction
ms.date: 03/30/2017
api_name:
- EPolicyAction
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EPolicyAction
helpviewer_keywords:
- EPolicyAction enumeration [.NET Framework hosting]
ms.assetid: 72dd76ba-239e-45ac-9ded-318fb07d6c6d
topic_type:
- apiref
ms.openlocfilehash: 72b371d72b2f055f2840da5595d9022ffd7e2507
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674753"
---
# <a name="epolicyaction-enumeration"></a>Перечисление EPolicyAction

Описание действий политики, которые узел может задать для операций, описанных в [еклроператион](eclroperation-enumeration.md) и ошибках, описанных в [еклрфаилуре](eclrfailure-enumeration.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eNoAction,  
    eThrowException,  
    eAbortThread,  
    eRudeAbortThread,  
    eUnloadAppDomain,  
    eRudeUnloadAppDomain,  
    eExitProcess,  
    eFastExitProcess,  
    eRudeExitProcess,  
    eDisableRuntime  
} EPolicyAction;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eAbortThread`|Указывает, что среда CLR должна корректно прерывать поток. Корректное прерывание включает попытки запуска всех `finally` блоков, все `catch` блоки, связанные с пределами потоков и методы завершения.|  
|`eDisableRuntime`|Указывает, что среда CLR должна перейти в отключенное состояние. В затронутом процессе не может быть выполнен дальнейший управляемый код, и потокам не удастся войти в среду CLR.|  
|`eExitProcess`|Указывает, что среда CLR должна попытаться корректно выйти из процесса, включая запуск методов завершения и выполнение операций очистки и ведения журнала.|  
|`eFastExitProcess`|Указывает, что среда CLR должна немедленно выйти из процесса, не запуская методы завершения, а также выполнять операции очистки и ведения журнала. Однако уведомление отправляется в отладчик.|  
|`eNoAction`|Указывает, что никакие действия не следует предпринимать.|  
|`eRudeAbortThread`|Указывает, что среда CLR должна выполнять грубое прерывание потока. Выполняются только `catch` те `finally` блоки и, которые помечены как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .|  
|`eRudeExitProcess`|Указывает, что среда CLR должна выйти из процесса без запуска методов завершения или ведения журнала.|  
|`eRudeUnloadAppDomain`|Указывает, что среда CLR должна выполнить грубую выгрузку <xref:System.AppDomain> . Выполняются только методы завершения, помеченные как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> . Аналогично, все потоки с этим <xref:System.AppDomain> в стеке получают `ThreadAbortException` , но выполняются только те `catch` блоки и, которые `finally` помечены как <xref:System.EnterpriseServices.MustRunInClientContextAttribute> .|  
|`eThrowException`|Указывает, что должно быть создано исключение, соответствующее условию, например нехватки памяти, переполнение буфера и т. д.|  
|`eUnloadAppDomain`|Указывает, что <xref:System.AppDomain> необходимо выгрузить. Среда CLR пытается запустить методы завершения.|  
  
## <a name="remarks"></a>Комментарии  

 Узел задает действия политики, вызывая методы интерфейса [ICLRPolicyManager](iclrpolicymanager-interface.md) . Сведения о принудительном и корректном аварийном завершении см. в разделе Перечисление [еклроператион](eclroperation-enumeration.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисление EClrFailure](eclrfailure-enumeration.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Интерфейс IHostPolicyManager](ihostpolicymanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
