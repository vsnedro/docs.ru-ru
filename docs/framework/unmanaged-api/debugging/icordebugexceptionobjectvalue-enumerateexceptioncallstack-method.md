---
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
ms.openlocfilehash: e45b180ac6d943d89740ad7ae10500ea4ad1aa9c
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975970"
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
 Если сведения о стеке вызовов недоступны, метод возвращает `S_OK`значение, а [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) — допустимый перечислитель с длиной 0. Если методу не удается получить сведения о трассировке стека, возвращается значение `E_FAIL` , а перечислитель не возвращается.  
  
 Объект [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md) отвечает за декодирование данных трассировки стека из `_stackTrace` поля объекта исключения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
