---
description: Дополнительные сведения о перечислении Еклрунхандледексцептион
title: Перечисление EClrUnhandledException
ms.date: 03/30/2017
api_name:
- EClrUnhandledException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrUnhandledException
helpviewer_keywords:
- EClrUnhandledException enumeration [.NET Framework hosting]
ms.assetid: d231044e-2b53-4836-93f9-8117ff0e5c3a
topic_type:
- apiref
ms.openlocfilehash: 088d448a92c4d9030208537b9c788477c85f9d37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785553"
---
# <a name="eclrunhandledexception-enumeration"></a>Перечисление EClrUnhandledException

Описывает доступные параметры для управления исключениями, которые не обрабатываются в пользовательском коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eRuntimeDeterminedPolicy,  
    eHostDeterminedPolicy  
} EClrUnhandledException;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eRuntimeDeterminedPolicy`|Указывает, что происходит поведение по умолчанию. Процесс разорван.|  
|`eHostDeterminedPolicy`|Указывает, что среда CLR не обрабатывает необработанные исключения и позволяет узлу определить дальнейшие действия.|  
  
## <a name="remarks"></a>Remarks  

 Чтобы указать, что среда CLR работает как более ранние версии, используйте `eHostDeterminedPolicy` член.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление EClrFailure](eclrfailure-enumeration.md)
- [Перечисление EClrOperation](eclroperation-enumeration.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Метод SetUnhandledExceptionPolicy](iclrpolicymanager-setunhandledexceptionpolicy-method.md)
- [Интерфейс IHostPolicyManager](ihostpolicymanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
