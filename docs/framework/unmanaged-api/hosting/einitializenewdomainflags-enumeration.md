---
description: Дополнительные сведения о перечислении EInitializeNewDomainFlags
title: Перечисление EInitializeNewDomainFlags
ms.date: 03/30/2017
api_name:
- EInitializeNewDomainFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EInitializeNewDomainFlags
helpviewer_keywords:
- EInitializeNewDomainFlags enumeration [.NET Framework hosting]
ms.assetid: 3a120ab2-f5ef-4c9b-8595-d3ed7247c342
ms.openlocfilehash: b856d061e86c0c79b35f842975378307b79a37e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785469"
---
# <a name="einitializenewdomainflags-enumeration"></a>Перечисление EInitializeNewDomainFlags

Позволяет узлу предоставлять среде выполнения сведения об инициализации домена приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eInitializeNewDomainFlags_None              = 0x0000,  
    eInitializeNewDomainFlags_NoSecurityChanges = 0x0002  
} EInitializeNewDomainFlags;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eInitializeNewDomainFlags_None`|Флаги отсутствуют.|  
|`eInitializeNewDomainFlags_NoSecurityChanges`|Информирует среду CLR о том, что узел не будет вносить изменения в состояние безопасности домена приложения в <xref:System.AppDomainManager.InitializeNewDomain%2A> методе.|  
  
## <a name="remarks"></a>Remarks  

 Метод [иклрдомаинманажер:: SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md) принимает параметр типа `EInitializeNewDomainFlags` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](hosting-enumerations.md)
- [Метод SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)
