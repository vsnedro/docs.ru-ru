---
title: Метод ICorDebugExceptionDebugEvent::GetNativeIP
ms.date: 03/30/2017
ms.assetid: 12e6a262-d9ac-49b8-9b80-1e653a2a3819
ms.openlocfilehash: 82dc892f3081c9f33ff7a2f363c326091f7cf039
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976035"
---
# <a name="icordebugexceptiondebugeventgetnativeip-method"></a>Метод ICorDebugExceptionDebugEvent::GetNativeIP
Получает собственный указатель инструкции для этого события отладки исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNativeIP(  
   [out]CORDB_ADDRESS *pIP  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pIP`  
 [out] Указатель на указатель инструкции для этого события отладки исключения. Дополнительные сведения см. в разделе «Примечания».  
  
## <a name="remarks"></a>Remarks  
 Смысл этого указателя инструкции стека зависит от типа события, как показано в следующей таблице.  
  
|Тип события.|Смысл значения `pStackPointer`|  
|----------------|--------------------------------------|  
|[MANAGED_EXCEPTION_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Адрес инструкции со сбоем.|  
|[MANAGED_EXCEPTION_USER_FIRST_CHANCE](cordebugrecordformat-enumeration.md)|Адрес кода в кадре, указанный методом [жетстаккпоинтер](icordebugexceptiondebugevent-getstackpointer-method.md) , где выполнение возобновится, если исключение не было вызвано. Исключение может вызывать или не вызывать другой код, например блок catch предложения `try/catch/finally`, выполняемый в этом фрейме.|  
|[MANAGED_EXCEPTION_CATCH_HANDLER_FOUND](cordebugrecordformat-enumeration.md)|Адрес кода, с `catch` которого начнется выполнение обработчика в кадре, указанном методом [жетстаккпоинтер](icordebugexceptiondebugevent-getstackpointer-method.md) .|  
|[MANAGED_EXCEPTION_UNHANDLED](cordebugrecordformat-enumeration.md)|`pIP` имеет значение 0.|  
  
 Тип события доступен в методе [ICorDebugDebugEvent:: GetEventKind](icordebugdebugevent-geteventkind-method.md) .  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICorDebugExceptionDebugEvent](icordebugexceptiondebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
