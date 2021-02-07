---
description: 'Дополнительные сведения о методе ICorDebugValue:: GetType'
title: Метод ICorDebugValue::GetType
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 750e73634683a03e811d2756cc62c16b6dcea3de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690331"
---
# <a name="icordebugvaluegettype-method"></a>Метод ICorDebugValue::GetType

Возвращает тип примитива этого объекта "ICorDebugValue".  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pType`  
 заполняет Указатель на значение перечисления "Корелементтипе", которое указывает тип значения.  
  
## <a name="remarks"></a>Remarks  

 Если объект является сложным типом времени выполнения, этот тип можно исследовать с помощью соответствующих подклассов `ICorDebugValue` интерфейса. Например, "ICorDebugObjectValue", который наследует от `ICorDebugValue` , представляет сложный тип.  
  
 `GetType`Методы и [ICorDebugObjectValue:: coclass](icordebugobjectvalue-getclass-method.md) возвращают сведения о типе значения. Они заменяются методом [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md) , поддерживающим универсальные шаблоны.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
