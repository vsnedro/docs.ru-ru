---
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
ms.openlocfilehash: 19731f34d259757e6de62dd4b4f0d4735d1c2e61
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706168"
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
  
 **.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Размещение перечислений](hosting-enumerations.md)
