---
description: 'Дополнительные сведения о методе: Икордебугкомобжектвалуе:: Жеткачединтерфацепоинтерс'
title: Метод ICorDebugComObjectValue::GetCachedInterfacePointers
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfacePointers
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers
helpviewer_keywords:
- ICorDebugComObjectValue::GetCachedInterfacePointers method [.NET Framework debugging]
- GetCachedInterfacePointers method, ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 08dbd558-bd39-4263-94c2-71e70687aaf0
topic_type:
- apiref
ms.openlocfilehash: 737d71f6aa903a3dfa97f583b47a322ec074147f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710859"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacepointers-method"></a>Метод ICorDebugComObjectValue::GetCachedInterfacePointers

Возвращает необработанные указатели интерфейса, кэшированные в текущей вызываемой оболочке времени выполнения (RCW).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCachedInterfacePointers(  
    [in] BOOL bIInspectableOnly,  
    [in] ULONG32 celt,  
    [out] ULONG32 *pceltFetched,  
    [out, size_is(celt), length_is(*pceltFetched) CORDB_ADDRESS *ptrs);  
```  
  
## <a name="parameters"></a>Параметры  

 `bIInspectableOnly`  
 окне Значение, указывающее, будет ли метод возвращать только среда выполнения Windows интерфейсы ( `IInspectable` интерфейсы) или все COM-интерфейсы, которые кэшируются вызываемой оболочкой времени выполнения (RCW).  
  
 `celt`  
 окне Число объектов, адреса которых необходимо получить.  
  
 `pceltFetched`  
 заполняет Указатель на число `CORDB_ADDRESS` значений, фактически возвращаемых в `ptrs` .  
  
 `ptrs`  
 Указатель на начальный адрес массива `CORDB_ADDRESS` значений, содержащих адреса кэшированных объектов интерфейса.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
