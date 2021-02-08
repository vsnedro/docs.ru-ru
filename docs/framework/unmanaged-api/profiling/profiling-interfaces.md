---
description: 'Дополнительные сведения: интерфейсы профилирования'
title: Профилирующие интерфейсы
ms.date: 04/10/2018
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], profiling
- profiling interfaces [.NET Framework]
- interfaces [.NET Framework profiling]
ms.assetid: d9303db8-e881-4217-91b7-8c7573c8ef9e
ms.openlocfilehash: d35931c0caad93116d7ea26d29020d84e48ebc29
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798931"
---
# <a name="profiling-interfaces"></a>Профилирующие интерфейсы

В этом разделе описываются неуправляемые интерфейсы, позволяющие профилировать программу, выполняемую в среде CLR.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Интерфейс ICLRProfiling](iclrprofiling-interface.md)  
 Предоставляет метод [AttachProfiler](iclrprofiling-attachprofiler-method.md) , который позволяет профилировщику присоединяться к выполняющемуся процессу.  
  
 [Интерфейс ICorProfilerAssemblyReferenceProvider](icorprofilerassemblyreferenceprovider-interface.md)  
 Позволяет профилировщику сообщать о CLR ссылок на сборки, которые профилировщик будет добавлять в обратный вызов [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .  
  
 [Интерфейс ICorProfilerCallback](icorprofilercallback-interface.md)  
 Предоставляет методы, используемые средой CLR для уведомления профилировщика кода при событиях, на которые подписан профилировщик.  
  
 [Интерфейс ICorProfilerCallback2](icorprofilercallback2-interface.md)  
 Расширяет интерфейс `ICorProfilerCallback` обратными вызовами, поддерживаемыми платформой .NET Framework 2.0 и более поздней версии.  
  
 [Интерфейс ICorProfilerCallback3](icorprofilercallback3-interface.md)  
 Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений о подключенном и отключенном состоянии профилировщику.  
  
 [Интерфейс ICorProfilerCallback4](icorprofilercallback4-interface.md)  
 Предоставляет методы обратного вызова, используемые средой CLR для передачи сведений профилировщику.  
  
 [Интерфейс ICorProfilerCallback5](icorprofilercallback5-interface.md)  
 Предоставляет метод, идентифицирующий транзитивное замыкание объектов, на которые ссылаются корни сборки мусора.  
  
 [Интерфейс ICorProfilerCallback6](icorprofilercallback6-interface.md)  
 Предоставляет метод обратного вызова, который используется средой CLR для уведомления профилировщика о загрузке сборки.  
  
 [Интерфейс ICorProfilerCallback7](icorprofilercallback7-interface.md)  
 Предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что поток символов, связанный с модулем в памяти, обновлен.  

[Интерфейс ICorProfilerCallback8](icorprofilercallback8-interface.md)  
Предоставляет методы обратного вызова, используемые средой CLR для уведомления профилировщика о начале и завершении JIT-компиляции динамического метода.

[Интерфейс ICorProfilerCallback9](icorprofilercallback9-interface.md)  
Предоставляет метод обратного вызова, используемый средой CLR для уведомления профилировщика о том, что динамический метод уничтожается сборщиком мусора и затем выгружается.

 [Интерфейс ICorProfilerFunctionControl](icorprofilerfunctioncontrol-interface.md)  
 Предоставляет методы, позволяющие профилировщику кода взаимодействовать со средой выполнения CLR и контролировать порядок генерирования кода JIT-компилятором при повторной компиляции указанного метода.  
  
 [Интерфейс ICorProfilerFunctionEnum](icorprofilerfunctionenum-interface.md)  
 Предоставляет методы для последовательного перебора коллекции функций в среде CLR.  
  
 [Интерфейс ICorProfilerInfo](icorprofilerinfo-interface.md)  
 Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.  
  
 [Интерфейс ICorProfilerInfo2](icorprofilerinfo2-interface.md)  
 Расширяет интерфейс `ICorProfilerInfo` методами, поддерживаемыми платформой .NET Framework 2.0 и более поздних версий.  
  
 [Интерфейс ICorProfilerInfo3](icorprofilerinfo3-interface.md)  
 Расширяет `ICorProfilerInfo2` интерфейс с помощью методов, поддерживаемых в платформа .NET Framework 4 и более поздних версий.  
  
 [Интерфейс ICorProfilerInfo4](icorprofilerinfo4-interface.md)  
 Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий и для запроса сведений.  
  
 [Интерфейс ICorProfilerInfo5](icorprofilerinfo5-interface.md)  
 Предоставляет методы, которые используются профилировщиками кода для взаимодействия со средой CLR с целью управления отслеживанием событий.  
  
 [Интерфейс ICorProfilerInfo6](icorprofilerinfo6-interface.md)  
 Предоставляет перечислитель для всех методов, принадлежащих заданному модулю NGen и встроенных в тело данного метода.  
  
 [Интерфейс ICorProfilerInfo7](icorprofilerinfo7-interface.md)  
 Предоставляет метод для применения новых заданных метаданных к модулю и предоставляет доступ к потоку символов в памяти.  
  
 [Интерфейс ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)  
 Предоставляет методы для последовательного перебора коллекции модулей, загруженных приложением или профилировщиком.  
  
 [Интерфейс ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md)  
 Предоставляет методы для последовательного прохода по коллекции замороженных объектов, созданных [Ngen.exe (генератор образов в машинном код)](../../tools/ngen-exe-native-image-generator.md).  
  
 [Интерфейс ICorProfilerThreadEnum](icorprofilerthreadenum-interface.md)  
 Предоставляет методы для последовательного перебора коллекции потоков в среде CLR.  
  
 [Интерфейс IMethodMalloc](imethodmalloc-interface.md)  
 Предоставляет метод [выделения](imethodmalloc-alloc-method.md) для выделения памяти для нового текста функции MSIL.  
  
## <a name="related-sections"></a>См. также  

 [Общие сведения о профилировании](profiling-overview.md)  
  
 [Глобальные статические функции профилирования](profiling-global-static-functions.md)  
  
 [Перечисления профилирования](profiling-enumerations.md)  
  
 [Структуры профилирования](profiling-structures.md)
