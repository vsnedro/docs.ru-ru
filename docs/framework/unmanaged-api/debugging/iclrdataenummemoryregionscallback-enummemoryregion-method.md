---
title: Метод ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
ms.openlocfilehash: b5ca524d223fad7ded0d56def3293eb40be69fa0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703724"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a>Метод ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion

Вызывается методом [иклрдатаенуммеморирегионс:: енуммеморирегионс](iclrdataenummemoryregions-enummemoryregions-method.md) для передачи в отладчик результата попытки перечисления указанной области памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `address`  
 окне Начальный адрес области памяти, которая должна быть перечислена.  
  
 `size`  
 окне Размер области памяти в байтах.  
  
## <a name="remarks"></a>Комментарии  

 `ICLRDataEnumMemoryRegions::EnumMemoryRegions`Метод будет вызывать этот метод обратного вызова после каждой попытки перечисления области памяти. Перечисление продолжится, даже если этот метод возвращает значение HRESULT, указывающее на сбой.  
  
 Регионы, сообщаемые этим обратным вызовом, могут быть дубликатами или перекрывающимися областями.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Клрдата. idl, Клрдата. h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRDataEnumMemoryRegionsCallback](iclrdataenummemoryregionscallback-interface.md)
