---
description: Дополнительные сведения о перечислении Екустомдумпфлавор
title: Перечисление ECustomDumpFlavor
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 3ef118368fc827472bdaacb0b03d8c2011275056
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785536"
---
# <a name="ecustomdumpflavor-enumeration"></a>Перечисление ECustomDumpFlavor

Содержит значения, указывающие, какие элементы следует включать в пользовательское подмножество дампа кучи при сообщении об ошибках.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|Указывает, что дамп пользовательской кучи должен запускаться как Малый дамп и включать дополнительные данные, указанные любыми экземплярами [кустомдумпитем](customdumpitem-structure.md) , передаваемыми в один и тот же метод.|  
|`DUMP_FLAVOR_NonHeapCLRState`|Указывает, что дамп пользовательской кучи должен собирать все данные состояния времени выполнения, которые не были выделены динамически.|  
  
## <a name="remarks"></a>Remarks  

 Параметр типа `ECustomDumpFlavor` передается методу [iclrerrorreportingmanagergetbucketparametersforcurrentexception:: BeginCustomDump](iclrerrorreportingmanager-begincustomdump-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисление ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)
- [Интерфейс ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)
- [Размещение перечислений](hosting-enumerations.md)
