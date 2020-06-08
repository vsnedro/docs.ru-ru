---
title: Перечисление EContextType
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
ms.openlocfilehash: b93b27957cc715a5b4718dd9ef61cd11f4a39914
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84493424"
---
# <a name="econtexttype-enumeration"></a>Перечисление EContextType
Описывает контекст безопасности выполняющегося в данный момент потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`eCurrentContext`|Указывает контекст текущего потока во время вызова средой CLR метода [IHostSecurityManager:: getsecuritycontext-](ihostsecuritymanager-getsecuritycontext-method.md) или контекста, ЗАПРАШИВАЕМого средой CLR при вызове метода [IHostSecurityManager:: SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md) .|  
|`eRestrictedContext`|Указывает контекст, для которого узел имеет более низкий уровень привилегий, например сборщик мусора, конструктор класса или модуля.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR предоставляет одно из `EContextType` значений в качестве значения параметра в вызовах `IHostSecurityManager::GetSecurityContext` `IHostSecurityManager::SetSecurityContext` методов и.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](ihostsecuritymanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
