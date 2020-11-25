---
title: Интерфейс ICorDebugFrame
ms.date: 03/30/2017
api_name:
- ICorDebugFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame
helpviewer_keywords:
- ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 0c48f764-3c64-4602-b2f4-4ffc60eb2c65
topic_type:
- apiref
ms.openlocfilehash: bdc17e2c6c63deae1420fe738eac51153f6b368e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726344"
---
# <a name="icordebugframe-interface"></a>Интерфейс ICorDebugFrame

Представляет кадр текущего стека.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateStepper](icordebugframe-createstepper-method.md)|Получает объект ICorDebugStepper, выполняющий пошаговые операции по отношению к этому `ICorDebugFrame` .|  
|[Метод GetCallee](icordebugframe-getcallee-method.md)|Возвращает указатель на объект `ICorDebugFrame` в текущей цепочке, который вызвал этот кадр, или возвращает значение null, если это внутренняя рамка в цепочке.|  
|[Метод GetCaller](icordebugframe-getcaller-method.md)|Возвращает указатель на объект `ICorDebugFrame` в текущей цепочке, вызвавшей этот кадр, или возвращает значение null, если это самый внешний кадр в цепочке.|  
|[Метод GetChain](icordebugframe-getchain-method.md)|Возвращает указатель на ICorDebugChain, частью которого `ICorDebugFrame` является.|  
|[Метод GetCode](icordebugframe-getcode-method.md)|Возвращает указатель на ICorDebugCode, связанный с этим кадром стека.|  
|[Метод GetFunction](icordebugframe-getfunction-method.md)|Возвращает указатель на ICorDebugFunction, содержащий код, связанный с этим кадром стека.|  
|[Метод GetFunctionToken](icordebugframe-getfunctiontoken-method.md)|Возвращает маркер метаданных для функции, которая содержит код, связанный с этим кадром стека.|  
|[Метод GetStackRange](icordebugframe-getstackrange-method.md)|Возвращает диапазон абсолютных адресов кадра стека, представленного этим объектом `ICorDebugFrame` .|  
  
## <a name="remarks"></a>Комментарии  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
