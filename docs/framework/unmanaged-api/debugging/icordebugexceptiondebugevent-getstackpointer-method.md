---
title: Метод ICorDebugExceptionDebugEvent::GetStackPointer
ms.date: 03/30/2017
ms.assetid: d8f66a1c-16be-4264-afc5-bc2dfbb4a682
ms.openlocfilehash: 46906e7d3ce7f257eb776e50dc6097946eb77d1f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95697406"
---
# <a name="icordebugexceptiondebugeventgetstackpointer-method"></a>Метод ICorDebugExceptionDebugEvent::GetStackPointer

Получает указатель стека для этого события отладки исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetStackPointer(  
   [out]CORDB_ADDRESS *pStackPointer  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pStackPointer`  
 [out] Указатель на адрес указателя стека для этого события отладки исключения. Дополнительные сведения см. в разделе "Примечания".  
  
## <a name="remarks"></a>Комментарии  

 Смысл этого указателя стека зависит от типа события, как показано в следующей таблице.  
  
|Тип события|Смысл значения `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Указатель стека для фрейма, вызвавшего исключение.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Указатель стека для фрейма пользовательского кода, ближайшего к точке вызванного исключения.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|Указатель стека для фрейма, содержащего обработчик catch.|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|Параметр `pStackPointer` имеет значение **NULL**.|  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
 Тип события доступен в методе [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
