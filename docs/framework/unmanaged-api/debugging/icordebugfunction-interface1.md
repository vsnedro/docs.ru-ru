---
title: Интерфейс ICorDebugFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction
helpviewer_keywords:
- ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: 783faea9-8083-41c1-b04a-51a81ac4c8f3
topic_type:
- apiref
ms.openlocfilehash: 668b27932ea7a2bdc244e1ac0bb8e6891cbd4d17
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726305"
---
# <a name="icordebugfunction-interface"></a>Интерфейс ICorDebugFunction

Представляет управляемую функцию или метод.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateBreakpoint](icordebugfunction-createbreakpoint-method.md)|Создает точку останова в начале этой функции.|  
|[Метод GetClass](icordebugfunction-getclass-method.md)|Возвращает объект ICorDebugClass, представляющий класс, членом которого является эта функция.|  
|[Метод GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md)|Возвращает номер версии последнего изменения, внесенного в эту функцию.|  
|[Метод GetILCode](icordebugfunction-getilcode-method.md)|Возвращает код MSIL для этой функции.|  
|[Метод GetLocalVarSigToken](icordebugfunction-getlocalvarsigtoken-method.md)|Возвращает маркер метаданных для сигнатуры локальной переменной функции, представленной этим `ICorDebugFunction` экземпляром.|  
|[Метод GetModule](icordebugfunction-getmodule-method.md)|Возвращает модуль, в котором определена эта функция.|  
|[Метод GetNativeCode](icordebugfunction-getnativecode-method.md)|Получает машинный код для этой функции.|  
|[Метод GetToken](icordebugfunction-gettoken-method.md)|Возвращает маркер метаданных для этой функции.|  
  
## <a name="remarks"></a>Комментарии  

 `ICorDebugFunction`Интерфейс не представляет функцию с параметрами универсального типа. Например, `ICorDebugFunction` экземпляр будет представлять, `Func<T>` но не `Func<string>` . Вызовите метод [ICorDebugILFrame2:: енумератетипепараметерс](icordebugilframe2-enumeratetypeparameters-method.md) , чтобы получить параметры универсального типа.  
  
 Связь между маркером метаданных метода, `mdMethodDef` и `ICorDebugFunction` объектом метода зависит от того, разрешена ли функция "изменить и продолжить" для функции:  
  
- Если функция "изменить и продолжить" не разрешена для функции, между `ICorDebugFunction` объектом и токеном существует связь "один к одному" `mdMethodDef` . То есть функция имеет один `ICorDebugFunction` объект и один `mdMethodDef` токен.  
  
- Если для функции разрешен режим "изменить и продолжить", между `ICorDebugFunction` объектом и токеном существует связь "многие к одному" `mdMethodDef` . Это значит, что функция может иметь много экземпляров `ICorDebugFunction` , по одной для каждой версии функции, но только один `mdMethodDef` токен.  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:**  Коргуидс. lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы отладки](debugging-interfaces.md)
