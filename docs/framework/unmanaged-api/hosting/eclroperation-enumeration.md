---
description: Дополнительные сведения о перечислении Еклроператион
title: Перечисление EClrOperation
ms.date: 03/30/2017
api_name:
- EClrOperation
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrOperation
helpviewer_keywords:
- EClrOperation enumeration [.NET Framework hosting]
ms.assetid: 5aef6808-5aac-4b2f-a2c7-fee1575c55ed
topic_type:
- apiref
ms.openlocfilehash: 9f75762a400955b5f36fb2a337f283e36a32658c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785566"
---
# <a name="eclroperation-enumeration"></a>Перечисление EClrOperation

Описывает набор операций, для которых узел может применять действия политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    OPR_ThreadAbort,  
    OPR_ThreadRudeAbortInNonCriticalRegion,  
    OPR_ThreadRudeAbortInCriticalRegion,  
    OPR_AppDomainUnload,  
    OPR_AppDomainRudeUnload,  
    OPR_ProcessExit,  
    OPR_FinalizerRun  
} EClrOperation;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`OPR_AppDomainRudeUnload`|Узел может указывать действия политики, которые будут выполняться, когда объект <xref:System.AppDomain> выгружается в некорректном (принудительном) режиме.|  
|`OPR_AppDomainUnload`|Узел может указывать действия политики, выполняемые при <xref:System.AppDomain> выгрузке.|  
|`OPR_FinalizerRun`|Узел может указывать действия политики, выполняемые при выполнении методов завершения.|  
|`OPR_ProcessExit`|Узел может указывать действия политики, выполняемые при завершении процесса.|  
|`OPR_ThreadAbort`|Узел может указывать действия политики, выполняемые при прерывании потока.|  
|`OPR_ThreadRudeAbortInCriticalRegion`|Узел может указывать действия политики, выполняемые при выполнении грубого прерывания потока в критической области кода.|  
|`OPR_ThreadRudeAbortInNonCriticalRegion`|Узел может указать действия политики, которые должны выполняться, когда грубое прерывание потока происходит в некритической области кода.|  
  
## <a name="remarks"></a>Remarks  

 Инфраструктура надежности среды CLR различает прерывания и сбои выделения ресурсов, происходящие в критических областях кода и происходящих в некритических областях кода. Это различие состоит в том, что узлы могут задавать разные политики в зависимости от того, где происходит сбой в коде.  
  
 *Критическая область кода* — это любое пространство, в котором среда CLR не может гарантировать, что прерывание задачи или невозможность завершения запроса ресурсов повлияет только на текущую задачу. Например, если задача удерживает блокировку и получает значение HRESULT, которое указывает на сбой при выполнении запроса на выделение памяти, недостаточно просто прервать эту задачу, чтобы обеспечить стабильность <xref:System.AppDomain> , поскольку <xref:System.AppDomain> может содержать другие задачи, ожидающие той же блокировки. Чтобы отказаться от текущей задачи, может привести к тому, что другие задачи перестанут отвечать на запросы. В этом случае ведущему приложению требуется возможность выгрузить всю, <xref:System.AppDomain> а не риск потенциально нестабильной работы.  
  
 С другой стороны, *некритическая область кода*— это регион, в котором CLR может гарантировать, что прерывание или сбой повлияет только на задачу, на которой возникла ошибка.  
  
 Среда CLR также различает корректное и некорректное (принудительное) прерывание. Как правило, обычное или корректное прерывание делает все усилия для выполнения подпрограмм обработки исключений и методов завершения перед прерыванием задачи, в то время как грубое прерывание не делает таких гарантий.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](eclrfailure-enumeration.md)
- [Перечисление EPolicyAction](epolicyaction-enumeration.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Интерфейс IHostPolicyManager](ihostpolicymanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
