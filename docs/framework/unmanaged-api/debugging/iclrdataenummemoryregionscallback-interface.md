---
title: Интерфейс ICLRDataEnumMemoryRegionsCallback
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback
helpviewer_keywords:
- ICLRDataEnumMemoryRegionsCallback interface [.NET Framework debugging]
ms.assetid: 3f1af8b0-8478-48e0-a7ec-3e90e0b97649
topic_type:
- apiref
ms.openlocfilehash: ddcb8064dfb9be30c66404a8762a9ca73cd6afe4
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860658"
---
# <a name="iclrdataenummemoryregionscallback-interface"></a>Интерфейс ICLRDataEnumMemoryRegionsCallback
Предоставляет метод обратного вызова для [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) , сообщающий отладчику результат попытки перечисления заданной области памяти.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumMemoryRegion](iclrdataenummemoryregionscallback-enummemoryregion-method.md)|Вызывается `ICLRDataEnumMemoryRegions::EnumMemoryRegions` с помощью для передачи в отладчик результата попытки перечисления заданной области памяти.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
