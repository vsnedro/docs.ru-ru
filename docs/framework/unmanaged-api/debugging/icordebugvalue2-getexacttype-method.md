---
description: 'Дополнительные сведения о методе: ICorDebugValue2:: GetExactType'
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
ms.openlocfilehash: d0ef08b119106ced89ec2094b5bf67d0c874b6bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690313"
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
  
## <a name="remarks"></a>Remarks  

 Метод с учетом универсальных шаблонов `GetExactType` заменяет методы [ICorDebugObjectValue::](icordebugobjectvalue-getclass-method.md) noreturn и [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) , каждый из которых возвращает сведения о типе значения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
