---
description: 'Дополнительные сведения о методе ICorDebugValue:: метода Address'
title: Метод ICorDebugValue::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetAddress
helpviewer_keywords:
- ICorDebugValue::GetAddress method [.NET Framework debugging]
- GetAddress method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: a247c792-45e1-4538-9e1f-b46acca4a463
topic_type:
- apiref
ms.openlocfilehash: c922388fbab820e50edffc140be94a2c0920099d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690435"
---
# <a name="icordebugvaluegetaddress-method"></a>Метод ICorDebugValue::GetAddress

Возвращает адрес этого объекта "ICorDebugValue", который находится в процессе отладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS   *pAddress  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAddress`  
 заполняет Указатель на `CORDB_ADDRESS` объект, указывающий адрес этого объекта значения.  
  
## <a name="remarks"></a>Remarks  

 Если значение недоступно, возвращается 0 (нуль). Это может произойти, если значение не меньше частично в регистрах или хранится в обработчике сборщика мусора ( `GCHandle` ).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
