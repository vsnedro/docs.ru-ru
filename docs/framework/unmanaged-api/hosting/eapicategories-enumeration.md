---
description: Дополнительные сведения о перечислении Еапикатегориес
title: Перечисление EApiCategories
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
ms.openlocfilehash: 58a7d4fa4d0c965bf9158ad6713185782d4ae94a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785631"
---
# <a name="eapicategories-enumeration"></a>Перечисление EApiCategories

Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eAll`|Указывает, что все управляемые классы и члены, охваченные другими `EApiCategories` полями, будут заблокированы в частично доверенном коде.|  
|`eExternalProcessMgmt`|Указывает, что управляемые классы и члены, разрешающие создание, обработку и уничтожение внешних процессов, блокируются в частично доверенном коде.|  
|`eExternalThreading`|Указывает, что управляемые классы и члены, которые позволяют блокировать создание, обработку и уничтожение внешних потоков, должны быть заблокированы в частично доверенном коде.|  
|`eMayLeakOnAbort`|Указывает, что управляемые типы и члены, которые могут привести к утечке памяти при прерывании, блокируются в частично доверенном коде.|  
|`eNoCategory`|Указывает, что ни одна из категорий управляемого кода не будет заблокирована в частично доверенном коде.|  
|`eSecurityInfrastructure`|Указывает, что инфраструктура безопасности среды CLR должна быть заблокирована для частично доверенного кода.|  
|`eSelfAffectingProcessMgmt`|Указывает, что управляемые классы и члены, возможности которых могут повлиять на работу размещенного процесса, должны быть заблокированы в частично доверенном коде.|  
|`eSelfAffectingThreading`|Указывает, что управляемые классы и члены, возможности которых могут влиять на потоки в размещенном процессе, блокируются в частично доверенном коде.|  
|`eSharedState`|Указывает, что управляемые классы и члены, которые предоставляют общее состояние, будут заблокированы для выполнения в частично доверенном коде.|  
|`eSynchronization`|Указывает, что классы и члены среды CLR, которые позволяют коду пользователя удерживать блокировки, блокируются в частично доверенном коде.|  
|`eUI`|Указывает, что управляемые классы и члены, которые разрешают или запрашивать взаимодействие с пользователем, блокируются в частично доверенном коде.|  
  
## <a name="remarks"></a>Remarks  

 Метод [иклрхостпротектионманажер:: SetProtectedCategories](iclrhostprotectionmanager-setprotectedcategories-method.md) принимает параметр типа `EApiCategories` .  
  
 `EApiCategories`Перечисление и `SetProtectedCategories` метод напрямую связаны с управляемым <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> классом. Управляемый класс используется с <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> перечислением, значения которого непосредственно соответствуют `EApiCategories` значениям, чтобы пометить управляемые типы и члены, которые предоставляют возможности, соответствующие категориям, описанным в `EApiCategories` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
