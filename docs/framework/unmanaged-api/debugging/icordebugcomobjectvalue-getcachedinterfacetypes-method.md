---
title: Метод ICorDebugComObjectValue::GetCachedInterfaceTypes
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
api_location:
- mscordbi.dll
f1_keywords:
- ICorDebugComObjectValue::GetCachedInterfaceTypes
helpviewer_keywords:
- GetCachedInterface method, ICorDebugComObjectValue interface [.NET Framework debugging]
- ICorDebugComObjectValue::GetCachedInterface method [.NET Framework debugging]
ms.assetid: d492284f-d3c5-4614-adb8-d718d5042500
topic_type:
- apiref
ms.openlocfilehash: 6b02657012870de4d0f888f6c05b115b25073fa2
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892830"
---
# <a name="icordebugcomobjectvaluegetcachedinterfacetypes-method"></a>Метод ICorDebugComObjectValue::GetCachedInterfaceTypes
Предоставляет перечислитель для типов интерфейса, которые текущий объект приводят к типу или используются в качестве.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCachedInterfaceTypes(  
    [in] BOOL bIInspectableOnly,  
    [out] ICorDebugTypeEnum **ppInterfacesEnum);  
```  
  
## <a name="parameters"></a>Параметры  
 `bIInspectableOnly`  
 окне Значение, указывающее, возвращает ли метод только среда выполнения Windows интерфейсы (`IInspectable` интерфейсы) или все COM-интерфейсы, кэшированные вызываемой оболочкой времени выполнения (RCW).  
  
 `ppInterfacesEnum`  
 заполняет Указатель на адрес перечислителя ICorDebugTypeEnum, который предоставляет доступ к объектам ICorDebugType, представляющим кэшированные типы интерфейсов, отфильтрованные в соответствии с `bIInspectableOnly`.  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
