---
description: Дополнительные сведения о перечислении Емеморяваилабле
title: Перечисление EMemoryAvailable
ms.date: 03/30/2017
api_name:
- EMemoryAvailable
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EMemoryAvailable
helpviewer_keywords:
- EMemoryAvailable enumeration [.NET Framework hosting]
ms.assetid: 38e72a06-dbed-473b-a59b-7e0b3ea4f2af
topic_type:
- apiref
ms.openlocfilehash: fdb33b45c354d39b1a52fd815a44041b659181ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785452"
---
# <a name="ememoryavailable-enumeration"></a>Перечисление EMemoryAvailable

Содержит значения, указывающие объем свободной физической памяти на компьютере. Эти значения логически сопоставляются с событиями для высокой и нехватки памяти, возвращаемой `CreateMemoryResourceNotification` функцией в Windows API.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eMemoryAvailableLow     = 1,  
    eMemoryAvailableNeutral = 2,  
    eMemoryAvailableHigh    = 3
} EMemoryAvailable;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eMemoryAvailableHigh`|Доступно достаточно физической памяти.|  
|`eMemoryAvailableLow`|Доступно очень мало физической памяти.|  
|`eMemoryAvailableNeutral`|Доступная физическая память не является нейтральной.|  
  
## <a name="remarks"></a>Remarks  

 Это значение передается узлом в среду CLR с помощью вызова метода [ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](hosting-enumerations.md)
