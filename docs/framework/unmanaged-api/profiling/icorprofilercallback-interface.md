---
description: 'Подробнее о: интерфейс ICorProfilerCallback'
title: Интерфейс ICorProfilerCallback
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback
helpviewer_keywords:
- ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type:
- apiref
ms.openlocfilehash: 5bc59839bfe352fb7d67688dcd7c8fe0d6c97eaf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705919"
---
# <a name="icorprofilercallback-interface"></a>Интерфейс ICorProfilerCallback

Предоставляет методы, которые используются средой CLR для уведомления профилировщика кода при возникновении событий, на которые подписан профилировщик.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md)|Уведомляет профилировщик о том, что домен приложения создан.|  
|[Метод AppDomainCreationStarted](icorprofilercallback-appdomaincreationstarted-method.md)|Уведомляет профилировщик о создании домена приложения.|  
|[Метод AppDomainShutdownFinished](icorprofilercallback-appdomainshutdownfinished-method.md)|Уведомляет профилировщик о том, что домен приложения был выгружен из процесса.|  
|[Метод AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md)|Уведомляет профилировщик о том, что домен приложения выгружается из процесса.|  
|[Метод AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md)|Уведомляет профилировщик о том, что загрузка сборки завершена.|  
|[Метод AssemblyLoadStarted](icorprofilercallback-assemblyloadstarted-method.md)|Уведомляет профилировщик о загрузке сборки.|  
|[Метод AssemblyUnloadFinished](icorprofilercallback-assemblyunloadfinished-method.md)|Уведомляет профилировщик о том, что сборка была выгружена.|  
|[Метод AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md)|Уведомляет профилировщик о выгрузке сборки.|  
|[Метод ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)|Уведомляет профилировщик о том, что загрузка класса завершена.|  
|[Метод ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)|Уведомляет профилировщик о том, что класс загружается.|  
|[Метод ClassUnloadFinished](icorprofilercallback-classunloadfinished-method.md)|Уведомляет профилировщик о завершении выгрузки класса.|  
|[Метод ClassUnloadStarted](icorprofilercallback-classunloadstarted-method.md)|Уведомляет профилировщик о выгрузке класса.|  
|[Метод COMClassicVTableCreated](icorprofilercallback-comclassicvtablecreated-method.md)|Уведомляет профилировщик о том, что вызываемая оболочка времени выполнения (RCW) для указанного IID и класса создана.|  
|[Метод COMClassicVTableDestroyed](icorprofilercallback-comclassicvtabledestroyed-method.md)|Уведомляет профилировщик о том, что обертка RCW уничтожается.|  
|[Метод ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)|Уведомляет профилировщик о том, что управление передается соответствующему `catch` блоку.|  
|[Метод ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)|Уведомляет профилировщик о том, что управление передается из соответствующего `catch` блока.|  
|[Метод ExceptionCLRCatcherExecute](icorprofilercallback-exceptionclrcatcherexecute-method.md)|Устарело в платформа .NET Framework версии 2,0.|  
|[Метод ExceptionCLRCatcherFound](icorprofilercallback-exceptionclrcatcherfound-method.md)|Устарело в платформа .NET Framework 2,0.|  
|[Метод ExceptionOSHandlerEnter](icorprofilercallback-exceptionoshandlerenter-method.md)|Не реализован. Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.|  
|[Метод ExceptionOSHandlerLeave](icorprofilercallback-exceptionoshandlerleave-method.md)|Не реализован. Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.|  
|[Метод ExceptionSearchCatcherFound](icorprofilercallback-exceptionsearchcatcherfound-method.md)|Уведомляет профилировщик о том, что на фазе поиска исключений обнаружен обработчик для созданного исключения.|  
|[Метод ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)|Уведомляет профилировщик о выполнении пользовательского фильтра.|  
|[Метод ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)|Уведомляет профилировщик о завершении выполнения фильтра пользователем.|  
|[Метод ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md)|Уведомляет профилировщик о том, что на фазе поиска исключений была задана функция.|  
|[Метод ExceptionSearchFunctionLeave](icorprofilercallback-exceptionsearchfunctionleave-method.md)|Уведомляет профилировщик о завершении фазы поиска обработки исключений при поиске функции.|  
|[Метод ExceptionThrown](icorprofilercallback-exceptionthrown-method.md)|Уведомляет профилировщик о том, что было создано исключение.|  
|[Метод ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)|Уведомляет профилировщик о том, что фаза очистки при обработке исключений вводит `finally` предложение, содержащееся в указанной функции.|  
|[Метод ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)|Уведомляет профилировщик о том, что фаза очистки в обработке исключений содержит `finally` предложение.|  
|[Метод ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)|Уведомляет профилировщик о том, что фаза очистки в обработке исключений вводит функцию.|  
|[Метод ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)|Уведомляет профилировщик о том, что фаза очистки в обработке исключений завершила очистку функции.|  
|[Метод FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md)|Уведомляет профилировщик о запуске среды выполнения для выгрузки функции.|  
|[Метод Initialize](icorprofilercallback-initialize-method.md)|Вызывается для инициализации профилировщика при запуске нового приложения CLR.|  
|[Метод JITCachedFunctionSearchFinished](icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Уведомляет профилировщик о завершении поиска для функции, которая была скомпилирована ранее с помощью NGen.exe.|  
|[Метод JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Уведомляет профилировщик о начале поиска для функции, которая была скомпилирована ранее с помощью NGen.exe.|  
|[Метод JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)|Уведомляет профилировщик о завершении компиляции функции JIT-компилятором.|  
|[Метод JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)|Уведомляет профилировщик о том, что JIT-компилятор начал компиляцию функции.|  
|[Метод JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)|Уведомляет профилировщик о том, что функция, скомпилированная JIT-компилятором, была удалена из памяти.|  
|[Метод JITInlining](icorprofilercallback-jitinlining-method.md)|Уведомляет профилировщик о том, что JIT-компилятор собирается вставить функцию в строку с другой функцией.|  
|[Метод ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)|Уведомляет профилировщик о том, что произошел переход из управляемого кода в неуправляемый код.|  
|[Метод ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md)|Уведомляет профилировщик о том, что модуль присоединен к своей родительской сборке.|  
|[Метод ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)|Уведомляет профилировщик о завершении загрузки модуля.|  
|[Метод ModuleLoadStarted](icorprofilercallback-moduleloadstarted-method.md)|Уведомляет профилировщик о загрузке модуля.|  
|[Метод ModuleUnloadFinished](icorprofilercallback-moduleunloadfinished-method.md)|Уведомляет профилировщик о завершении выгрузки модуля.|  
|[Метод ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md)|Уведомляет профилировщик о выгрузке модуля.|  
|[Метод MovedReferences](icorprofilercallback-movedreferences-method.md)|Уведомляет профилировщик о ссылках на объекты, которые были перемещены во время сборки мусора.|  
|[Метод ObjectAllocated](icorprofilercallback-objectallocated-method.md)|Уведомляет профилировщик о том, что память в куче была выделена для объекта.|  
|[Метод ObjectReferences](icorprofilercallback-objectreferences-method.md)|Уведомляет профилировщик об объектах в памяти, на которые ссылается указанный объект.|  
|[Метод ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)|Уведомляет профилировщик о количестве экземпляров каждого указанного класса, которые были созданы с момента предыдущей сборки мусора.|  
|[Метод RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)|Уведомляет профилировщик о том, что вызов удаленного взаимодействия был выполнен до завершения на клиенте.|  
|[Метод RemotingClientInvocationStarted](icorprofilercallback-remotingclientinvocationstarted-method.md)|Уведомляет профилировщик о начале удаленного вызова.|  
|[Метод RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md)|Уведомляет профилировщик о завершении серверной части удаленного вызова, а также о получении и обработке ответа клиентом.|  
|[Метод RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)|Уведомляет профилировщик о том, что клиент отправляет запрос на сервер.|  
|[Метод RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md)|Уведомляет профилировщик о том, что процесс завершил вызов метода в ответ на запрос удаленного вызова метода.|  
|[Метод RemotingServerInvocationStarted](icorprofilercallback-remotingserverinvocationstarted-method.md)|Уведомляет профилировщик о том, что процесс вызывает метод в ответ на запрос удаленного вызова метода.|  
|[Метод RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md)|Уведомляет профилировщик о том, что процесс получает удаленный вызов метода или запрос на активацию.|  
|[Метод RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)|Уведомляет профилировщик о том, что процесс завершил обработку запроса удаленного вызова метода и собирается передать ответ через канал.|  
|[Метод RootReferences](icorprofilercallback-rootreferences-method.md)|Уведомляет профилировщик о получении сведений о корневых ссылках после сборки мусора.|  
|[Метод RuntimeResumeFinished](icorprofilercallback-runtimeresumefinished-method.md)|Уведомляет профилировщик о том, что среда выполнения возобновила все потоки среды выполнения и вернула нормальную работу.|  
|[Метод RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)|Уведомляет профилировщик о том, что среда выполнения возобновляет все потоки времени выполнения.|  
|[Метод RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)|Уведомляет профилировщик о том, что среда выполнения прервал приостановленную приостановку времени выполнения.|  
|[Метод RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)|Уведомляет профилировщик о том, что среда выполнения завершила приостановку всех потоков времени выполнения.|  
|[Метод RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)|Уведомляет профилировщик о том, что среда выполнения собирается приостановить все потоки времени выполнения.|  
|[Метод RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)|Уведомляет профилировщик о том, что указанный поток возобновил работу после приостановки.|  
|[Метод RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)|Уведомляет профилировщик о том, что указанный поток был или находится в состоянии приостановки.|  
|[Метод Shutdown](icorprofilercallback-shutdown-method.md)|Уведомляет профилировщик о том, что приложение завершает работу.|  
|[Метод ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)|Уведомляет профилировщик о том, что управляемый поток реализуется с помощью определенного потока операционной системы (ОС).|  
|[Метод ThreadCreated](icorprofilercallback-threadcreated-method.md)|Уведомляет профилировщик о том, что поток был создан.|  
|[Метод ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md)|Уведомляет профилировщик о том, что поток был уничтожен.|  
|[Метод UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md)|Уведомляет профилировщик о том, что произошел переход из неуправляемого кода в управляемый код.|  
  
## <a name="remarks"></a>Remarks  

 Среда CLR вызывает метод в `ICorProfilerCallback` интерфейсе (или [ICorProfilerCallback2](icorprofilercallback2-interface.md)) для уведомления профилировщика при возникновении события, на которое подписан профилировщик. Это основной интерфейс обратного вызова, с помощью которого среда CLR взаимодействует с профилировщиком кода.  
  
 Профилировщик кода должен реализовывать методы `ICorProfilerCallback` интерфейса. Для платформа .NET Framework версии 2,0 или более поздней профилировщик также должен реализовать `ICorProfilerCallback2` методы. Каждая реализация метода должна возвращать HRESULT со значением S_OK в случае успеха или E_FAIL при сбое. В настоящее время среда CLR игнорирует значение HRESULT, возвращаемое каждым обратным вызовом, за исключением значения [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
 В реестре Microsoft Windows профилировщик кода должен зарегистрировать объект модели COM, реализующий `ICorProfilerCallback` `ICorProfilerCallback2` интерфейсы и. Профилировщик кода подписывается на события, для которых требуется получать уведомления путем вызова [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Обычно это делается в реализации метода [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md)профилировщика. Затем профилировщик может получать уведомления от среды выполнения, когда событие собирается или было только что произошло в процессе выполнения.  
  
> [!NOTE]
> Профилировщик регистрирует один COM-объект. Если профилировщик предназначен для платформа .NET Framework версии 1,0 или 1,1, этот COM-объект должен реализовывать только методы класса `ICorProfilerCallback` . Если он предназначен для платформа .NET Framework версии 2,0 или более поздней, COM-объект также должен реализовывать методы `ICorProfilerCallback2` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorProf.idl, CorProf.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Профилирующие интерфейсы](profiling-interfaces.md)
- [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Интерфейс ICorProfilerCallback3](icorprofilercallback3-interface.md)
- [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)
