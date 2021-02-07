---
description: 'Дополнительные сведения о методе: ICorDebugExceptionObjectValue:: EnumerateExceptionCallStack'
title: Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 97918d280299fae16eb55185baee19c27d99005b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693282"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>Метод ICorDebugExceptionObjectValue::EnumerateExceptionCallStack

Возвращает перечислитель для стека вызовов, внедренного в объект исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 ппкаллстаккенум  
 заполняет Указатель на адрес объекта интерфейса [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) , который является перечислителем трассировки стека для управляемого объекта исключения.  
  
## <a name="remarks"></a>Remarks  

 Если сведения о стеке вызовов недоступны, метод возвращает значение `S_OK` , а [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) — допустимый перечислитель с длиной 0. Если методу не удается получить сведения о трассировке стека, возвращается значение, `E_FAIL` а перечислитель не возвращается.  
  
 Объект [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) отвечает за декодирование данных трассировки стека из `_stackTrace` поля объекта исключения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
