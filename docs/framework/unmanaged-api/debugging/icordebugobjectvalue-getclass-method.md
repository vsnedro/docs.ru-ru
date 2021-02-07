---
description: 'Дополнительные сведения о методе: ICorDebugObjectValue:: coclass'
title: Метод ICorDebugObjectValue::GetClass
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: 4ea6a47814777da934aa14bba947a047c075396c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722221"
---
# <a name="icordebugobjectvaluegetclass-method"></a>Метод ICorDebugObjectValue::GetClass

Возвращает класс этого значения объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppClass`  
 заполняет Указатель на адрес объекта "ICorDebugClass", который представляет класс значения объекта, представленного этим объектом "ICorDebugObjectValue".  
  
## <a name="remarks"></a>Remarks  

 `GetClass`Методы и [ICorDebugValue:: GetType](icordebugvalue-gettype-method.md) возвращают сведения о типе значения; они заменяются универсальными классами [ICorDebugValue2:: GetExactType](icordebugvalue2-getexacttype-method.md).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
