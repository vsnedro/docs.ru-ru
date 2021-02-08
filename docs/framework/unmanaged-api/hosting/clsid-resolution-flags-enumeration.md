---
description: 'Дополнительные сведения: перечисление CLSID_RESOLUTION_FLAGS'
title: Перечисление CLSID_RESOLUTION_FLAGS
ms.date: 03/30/2017
api_name:
- CLSID_RESOLUTION_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLSID_RESOLUTION_FLAGS
helpviewer_keywords:
- CLSID_RESOLUTION_FLAGS enumeration [.NET Framework hosting]
ms.assetid: cd8b9879-962a-4811-aa46-2e2b6bae0d84
topic_type:
- apiref
ms.openlocfilehash: 54d334147e13217f8ce20dae1b139cdc6d11a3b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799880"
---
# <a name="clsid_resolution_flags-enumeration"></a>Перечисление CLSID_RESOLUTION_FLAGS

Содержит значения, которые указывают, как общеязыковая среда выполнения (CLR) должна разрешать `CLSID` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    CLSID_RESOLUTION_DEFAULT      = 0x0,  
    CLSID_RESOLUTION_REGISTERED   = 0x1  
} CLSID_RESOLUTION_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`CLSID_RESOLUTION_DEFAULT`|Указывает поведение по умолчанию.|  
|`CLSID_RESOLUTION_REGISTERED`|Указывает, что среда выполнения выполняет поиск в реестре и применяет политику оболочки совместимости.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](hosting-enumerations.md)
