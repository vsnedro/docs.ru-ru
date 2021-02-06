---
description: 'Дополнительные сведения о методе ICorProfilerCallback:: Shutdown'
title: Метод ICorProfilerCallback::Shutdown
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.Shutdown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::Shutdown
helpviewer_keywords:
- ICorProfilerCallback::Shutdown method [.NET Framework profiling]
- Shutdown method [.NET Framework profiling]
ms.assetid: 1ea194f0-a331-4855-a2ce-37393b8e5f84
topic_type:
- apiref
ms.openlocfilehash: 7afc274579f248ee190e379160f2709b5cb9881a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657324"
---
# <a name="icorprofilercallbackshutdown-method"></a>Метод ICorProfilerCallback::Shutdown

Уведомляет профилировщик о том, что приложение завершает работу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Shutdown();  
```  
  
## <a name="remarks"></a>Remarks  

 Код профилировщика не может безопасно вызывать методы интерфейса [ICorProfilerInfo](icorprofilerinfo-interface.md) после `Shutdown` вызова метода. Все вызовы `ICorProfilerInfo` методов приводят к неопределенному поведению после `Shutdown` возврата метода. Некоторые неизменяемые события по-прежнему могут возникать после завершения работы. Профилировщик должен немедленно возвращаться к моменту, когда это происходит.  
  
 `Shutdown`Метод будет вызываться только в том случае, если управляемое приложение, профилирование которого запускается как управляемый код (т. е. исходный кадр в стеке процессов является управляемым). Если приложение запущено в виде неуправляемого кода, но позднее перейдет в управляемый код, то создание экземпляра среды CLR `Shutdown` не будет вызвано. В таких случаях профилировщик должен включать в свою библиотеку `DllMain` подпрограммы, которая использует значение DLL_PROCESS_DETACH для высвобождения любых ресурсов и выполнения очистки данных, таких как сброс трассировок на диск и т. д.  
  
 Как правило, профилировщик должен справляться с непредвиденным завершением работы. Например, процесс может быть остановлен `TerminateProcess` методом Win32's (объявлен в винбасе. h). В других случаях среда CLR остановит определенные управляемые потоки (фоновые потоки), не создавая для них сообщения с неупорядоченным уничтожением.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)
- [Метод Initialize](icorprofilercallback-initialize-method.md)
