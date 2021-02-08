---
description: 'Дополнительные сведения: перечисление HOST_TYPE'
title: Перечисление HOST_TYPE
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: 6a0baf3050f99885953ddec06342cbe19accfef3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785241"
---
# <a name="host_type-enumeration"></a>Перечисление HOST_TYPE

Содержит значения, указывающие тип узла, запускающего приложение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|Запустите приложение из AppLaunch.exe.<br /><br /> Используйте это значение для частично доверенных приложений.|  
|`HOST_TYPE_CORFLAG`|Запустите приложение напрямую. То есть запустите приложение из собственного EXE-файла.<br /><br /> Используйте это значение для полностью доверенных приложений.|  
|`HOST_TYPE_DEFAULT`|То же, что и HOST_TYPE_APPLAUNCH.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](hosting-enumerations.md)
