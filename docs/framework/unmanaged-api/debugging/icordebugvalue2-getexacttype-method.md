---
title: Метод ICorDebugValue2::GetExactType
ms.date: 03/30/2017
api_name:
- ICorDebugValue2.GetExactType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue2::GetExactType
helpviewer_keywords:
- ICorDebugValue2::GetExactType method [.NET Framework debugging]
- GetExactType method [.NET Framework debugging]
ms.assetid: 8e9aae1b-d1b7-4b6e-b577-6faf36dcec85
topic_type:
- apiref
ms.openlocfilehash: cb5bec66ab02de248109d8aaf444a93e67c2c6d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720364"
---
# <a name="icordebugvalue2getexacttype-method"></a>Метод ICorDebugValue2::GetExactType

Возвращает указатель интерфейса на объект "ICorDebugType", представляющий <xref:System.Type> это значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetExactType (  
    [out] ICorDebugType   **ppType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppType`  
 заполняет Указатель на адрес `ICorDebugType` объекта, представляющий <xref:System.Type> значение, представленное этим объектом "ICorDebugValue2".  
  
## <a name="remarks"></a>Комментарии  

 Метод с учетом универсальных шаблонов `GetExactType` заменяет методы [ICorDebugObjectValue::](icordebugobjectvalue-getclass-method.md) noreturn и [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , каждый из которых возвращает сведения о типе значения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел
