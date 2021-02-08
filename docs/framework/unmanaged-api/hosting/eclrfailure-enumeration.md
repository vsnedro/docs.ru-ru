---
description: Дополнительные сведения о перечислении Еклрфаилуре
title: Перечисление EClrFailure
ms.date: 03/30/2017
api_name:
- EClrFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrFailure
helpviewer_keywords:
- EClrFailure enumeration [.NET Framework hosting]
ms.assetid: 37b95cce-9bfb-4ecf-a00b-33dcba782c67
topic_type:
- apiref
ms.openlocfilehash: 9f3a2270651e5b05d2d31ed90511b8eb05dd4d44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785592"
---
# <a name="eclrfailure-enumeration"></a>Перечисление EClrFailure

Описывает набор сбоев, для которых узел может задавать действия политики.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    FAIL_NonCriticalResource,  
    FAIL_CriticalResource,  
    FAIL_FatalRuntime,  
    FAIL_OrphanedLock  
    FAIL_StackOverflow  
    FAIL_AccessViolation  
    FAIL_CodeContract  
} EClrFailure;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`FAIL_NonCriticalResource`|Произошла ошибка при попытке выделения ресурса (например, потока, блока памяти или блокировки) в некритической области кода.|  
|`FAIL_CriticalResource`|Произошла ошибка при попытке выделения ресурса (например, потока, блока памяти или блокировки) в критической области кода.|  
|`FAIL_FatalRuntime`|Общеязыковая среда выполнения (CLR) больше не может выполнять управляемый код в процессе. Исходя этого, вызовы любых функций размещения возвращают значение HRESULT, равное HOST_E_CLRNOTAVAILABLE.|  
|`FAIL_OrphanedLock`|Потоку не удалось снять блокировку после возврата из <xref:System.AppDomain> объекта. Узлу не удается установить этот сбой, чтобы привести к прерыванию потока.|  
|`FAIL_StackOverflow`|Произошло переполнение стека.|  
|`FAIL_AccessViolation`|Предпринята попытка чтения или записи в защищенную память. Не поддерживается в платформа .NET Framework 4.|  
|`FAIL_CodeContract`|Ошибка контракта кода. См. раздел [контракты кода](../../debug-trace-profile/code-contracts.md).|  
  
## <a name="remarks"></a>Remarks  

 Список значений [еполициактион](epolicyaction-enumeration.md) , которые узел может использовать для указания действий политики для условий сбоя, см. в описании метода [ICLRPolicyManager:: сетактиононфаилуре](iclrpolicymanager-setactiononfailure-method.md) . Дополнительные сведения о критических и некритических областях кода см. в разделе [еклроператион](eclroperation-enumeration.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Метод SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md)
- [Интерфейс IHostPolicyManager](ihostpolicymanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
