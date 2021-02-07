---
description: 'Дополнительные сведения: Отладка интерфейсов'
title: Интерфейсы отладки
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 6e6cc07e200b9ecf6bf4039f4fd5fd69e27b6fda
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717970"
---
# <a name="debugging-interfaces"></a>Интерфейсы отладки

В этом разделе описываются неуправляемые интерфейсы отладки, управляющие отладкой программы, выполняемой в среде CLR.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Интерфейс Иклрдатаенуммеморирегионс](iclrdataenummemoryregions-interface.md)\
 Предоставляет метод, выполняющий перечисление областей памяти, заданной вызовами.  
  
 [Интерфейс Иклрдатаенуммеморирегионскаллбакк](iclrdataenummemoryregionscallback-interface.md)\
 Предоставляет метод обратного вызова для метода `EnumMemoryRegions`, сообщающий отладчику результат попытки перечисления заданной области памяти.  
  
 [Интерфейс ICLRDataTarget](iclrdatatarget-interface.md)\
 Предоставляет методы для взаимодействия с целевым процессом среды CLR.  
  
 [Интерфейс ICLRDataTarget2](iclrdatatarget2-interface.md)\
 Подкласс `ICLRDataTarget`, используемый уровнем служб доступа к данным с целью управления областями виртуальной памяти в целевом процессе.  
  
 [Интерфейс метод iclrdatatarget3](iclrdatatarget3-interface.md)\
 Подкласс [ICLRDataTarget2](iclrdatatarget2-interface.md) , предоставляющий доступ к сведениям об исключениях.  
  
 [Интерфейс ICLRDebugging](iclrdebugging-interface.md)\
 Предоставляет методы, обрабатывающие загрузку и выгрузку модулей для отладки.  
  
 [Интерфейс Иклрдебуггинглибрарипровидер](iclrdebugginglibraryprovider-interface.md)\
 Включает метод [метода ProvideLibrary](iclrdebugginglibraryprovider-providelibrary-method.md) , который получает интерфейс обратного вызова поставщика библиотеки, который позволяет находить и загружать библиотеки отладки, относящиеся к конкретной версии среды CLR, по запросу.  
  
 [Интерфейс Иклрметадаталокатор](iclrmetadatalocator-interface.md)\
 Интерфейс, используемый уровнем служб доступа к данным для определения местонахождения метаданных сборок в целевом процессе.  
  
 [Интерфейс ICorDebug](icordebug-interface.md)\
 Предоставляет методы, позволяющие разработчикам отлаживать приложения в среде CLR.  
  
 [Интерфейс ICorDebugAppDomain](icordebugappdomain-interface.md)\
 Предоставляет методы для отладки доменов приложения.  
  
 [Интерфейс ICorDebugAppDomain2](icordebugappdomain2-interface.md)\
 Предоставляет методы для работы с массивами, указателями, указателями функций и типами ByRef. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain`.  
  
 [Интерфейс ICorDebugAppDomain3](icordebugappdomain3-interface.md)\
 Предоставляет методы для работы с типами среда выполнения Windows в домене приложения. Этот интерфейс является расширением интерфейса `ICorDebugAppDomain` и `ICorDebugAppDomain2`.  
  
 [Интерфейс ICorDebugAppDomain4](icordebugappdomain4-interface.md)\
 Логически расширяет интерфейс [ICorDebugAppDomain](icordebugappdomain-interface.md) для получения управляемого объекта из вызываемой оболочки COM.  
  
 [Интерфейс Икордебугаппдомаиненум](icordebugappdomainenum-interface.md)\
 Предоставляет метод, возвращающий заданное число значений `ICorDebugAppDomain`, начиная со следующего расположения в перечислении.  
  
 [Интерфейс ICorDebugArrayValue](icordebugarrayvalue-interface.md)\
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий одномерный или многомерный массив.  
  
 [Интерфейс ICorDebugAssembly](icordebugassembly-interface.md)\
 Представляет сборку.  
  
 [Интерфейс ICorDebugAssembly2](icordebugassembly2-interface.md)\
 Представляет сборку. Этот интерфейс является расширением интерфейса `ICorDebugAssembly`.  
  
 [Интерфейс ICorDebugAssembly3](icordebugassembly3-interface.md)\
 Логически расширяет интерфейс [ICorDebugAssembly](icordebugassembly-interface.md) , чтобы обеспечить поддержку для сборок контейнеров и содержащихся в них сборок. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugAssemblyEnum](icordebugassemblyenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugAssembly`.  
  
 [Интерфейс Икордебугблоккингобжектенум](icordebugblockingobjectenum-interface.md)\
 Предоставляет перечислитель для списка структур [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
 [Интерфейс Икордебугбоксвалуе](icordebugboxvalue-interface.md)\
 Подкласс интерфейса `ICorDebugHeapValue`, представляющий упакованное значение объектов класса.  
  
 [Интерфейс Икордебугбреакпоинт](icordebugbreakpoint-interface.md)\
 Представляет точку останова в функции или контрольную точку для значения.  
  
 [Интерфейс ICorDebugBreakpointEnum](icordebugbreakpointenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugBreakpoint`.  
  
 [Интерфейс ICorDebugChain](icordebugchain-interface.md)\
 Представляет сегмент физического или логического стека вызовов.  
  
 [Интерфейс Икордебугчаиненум](icordebugchainenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugChain`.  
  
 [Интерфейс ICorDebugClass](icordebugclass-interface.md)\
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсальный, `ICorDebugClass` представляет универсальный тип, у которого отсутствуют экземпляры.  
  
 [Интерфейс ICorDebugClass2](icordebugclass2-interface.md)\
 Представляет универсальный класс или класс параметром метода типа <xref:System.Type>. Этот интерфейс расширяет интерфейс `ICorDebugClass`.  
  
 [Интерфейс ICorDebugCode](icordebugcode-interface1.md)\
 Представляет сегмент кода на языке MSIL или сегмент машинного кода.  
  
 [Интерфейс ICorDebugCode2](icordebugcode2-interface.md)\
 Предоставляет методы, расширяющие возможности интерфейса `ICorDebugCode`.  
  
 [Интерфейс ICorDebugCode3](icordebugcode3-interface.md)\
 Предоставляет метод, расширяющий интерфейс [ICorDebugCode](icordebugcode-interface1.md) и [ICorDebugCode2](icordebugcode2-interface.md) для предоставления сведений об управляемом возвращаемом значении.  
  
 [Интерфейс ICorDebugCode4](icordebugcode4-interface.md)\
 Предоставляет метод, позволяющий отладчику перечислить локальные переменные и аргументы в функции.  
  
 [Интерфейс Икордебугкодинум](icordebugcodeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugCode`.  
  
 [Интерфейс Икордебугкомобжектвалуе](icordebugcomobjectvalue-interface.md)\
 Предоставляет методы для получения кэшированных объектов интерфейса.  
  
 [Интерфейс Икордебугконтекст](icordebugcontext-interface.md)\
 Представляет объект контекста. Этот интерфейс еще не реализован.  
  
 [Интерфейс ICorDebugController](icordebugcontroller-interface.md)\
 Представляет область (<xref:System.Diagnostics.Process> или <xref:System.AppDomain>), в которой можно осуществлять управление контекстом выполнения кода.  
  
 [Интерфейс ICorDebugDataTarget](icordebugdatatarget-interface.md)\
 Предоставляет интерфейс обратного вызова, обеспечивающий доступ к конкретному целевому процессу.  
  
 [Интерфейс метод icordebugdatatarget2](icordebugdatatarget2-interface.md)\
 Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) . **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugDataTarget3](icordebugdatatarget3-interface.md)\
 Логически расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) , чтобы предоставить сведения о загруженных модулях. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)\
 Определяет базовый интерфейс, из которого возникают все события отладки `ICorDebug`. **Доступен только в .NET Native.**  
  
 [Интерфейс Икордебужедитандконтинуирроринфо](icordebugeditandcontinueerrorinfo-interface.md)\
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс метод icordebugeditandcontinuesnapshot](icordebugeditandcontinuesnapshot-interface.md)\
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс ICorDebugEnum](icordebugenum-interface1.md)\
 Служит абстрактным базовым интерфейсом для перечислителей отладки.  
  
 [Интерфейс ICorDebugErrorInfoEnum](icordebugerrorinfoenum-interface.md)\
 Является устаревшей. Не следует использовать данный интерфейс.  
  
 [Интерфейс ICorDebugEval](icordebugeval-interface.md)\
 Предоставляет методы, позволяющие отладчику выполнять код в контексте отлаживаемого кода.  
  
 [Интерфейс ICorDebugEval2](icordebugeval2-interface.md)\
 Расширяет интерфейс `ICorDebugEval` для предоставления поддержки универсальных типов.  
  
 [Интерфейс Икордебужексцептиондебужевент](icordebugexceptiondebugevent-interface.md)\
 Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий исключения. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)\
 Предоставляет перечислитель для сведений стека вызовов, встроенных в объект исключения.  
  
 [Интерфейс ICorDebugExceptionObjectValue](icordebugexceptionobjectvalue-interface.md)\
 Расширяет интерфейс [ICorDebugObjectValue](icordebugobjectvalue-interface.md) для предоставления сведений о трассировке стека из управляемого объекта исключения.  
  
 [Интерфейс ICorDebugFrame](icordebugframe-interface.md)\
 Представляет кадр текущего стека.  
  
 [Интерфейс ICorDebugFrameEnum](icordebugframeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugFrame`.  
  
 [Интерфейс ICorDebugFunction](icordebugfunction-interface1.md)\
 Представляет управляемую функцию или метод.  
  
 [Интерфейс ICorDebugFunction2](icordebugfunction2-interface.md)\
 Локально расширяет интерфейс `ICorDebugFunction` для предоставления поддержки отладки в пошаговом режиме "Только мой код".  
  
 [Интерфейс ICorDebugFunction3](icordebugfunction3-interface.md)\
 Логически расширяет интерфейс [ICorDebugFunction](icordebugfunction-interface1.md) , чтобы предоставить доступ к коду из запроса ReJIT.  
  
 [Интерфейс ICorDebugFunctionBreakpoint](icordebugfunctionbreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для поддержки точек останова в функциях.  
  
 [Интерфейс ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)\
 Предоставляет перечислитель для объектов, для которых будет выполнена сборка мусора.  
  
 [Интерфейс ICorDebugGenericValue](icordebuggenericvalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, применяемый ко всем значениям. Этот интерфейс предоставляет для значения методы Get и Set.  
  
 [Интерфейс ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)\
 Предоставляет перечислитель для объекта, сопоставляющего идентификаторы GUID и соответствующие объекты `ICorDebugType`.  
  
 [Интерфейс ICorDebugHandleValue](icordebughandlevalue-interface.md)\
 Подкласс интерфейса `ICorDebugReferenceValue`, представляющий значение ссылки, для которого отладчик создал дескриптор сборки мусора.  
  
 [Интерфейс Икордебугхеапенум](icordebugheapenum-interface.md)\
 Предоставляет перечислитель для объектов в управляемой куче.  
  
 [Интерфейс Икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md)\
 Предоставляет перечислитель для областей памяти управляемой кучи.  
  
 [Интерфейс ICorDebugHeapValue](icordebugheapvalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, представляющий объект, подобранный сборщиком мусора среды CLR.  
  
 [Интерфейс ICorDebugHeapValue2](icordebugheapvalue2-interface1.md)\
 Расширение интерфейса `ICorDebugHeapValue`, предоставляющее поддержку дескрипторов среды выполнения.  
  
 [Интерфейс ICorDebugHeapValue3](icordebugheapvalue3-interface.md)\
 Предоставляет свойства блокировки монитора объектов.  
  
 [Интерфейс Икордебугилкоде](icordebugilcode-interface.md)\
 Представляет сегмент кода промежуточного языка.  
  
 [Интерфейс ICorDebugILCode2](icordebugilcode2-interface.md)\
 Логически расширяет интерфейс [икордебугилкоде](icordebugilcode-interface.md) , чтобы предоставить методы, которые возвращают маркер для сигнатуры локальной переменной функции и сопоставляют смещенные промежуточные языки (IL) профилировщика с исходными смещениями Il метода.  
  
 [Интерфейс ICorDebugILFrame](icordebugilframe-interface.md)\
 Предоставляет кадр стека кода MSIL.  
  
 [Интерфейс ICorDebugILFrame2](icordebugilframe2-interface.md)\
 Логическое расширение интерфейса `ICorDebugILFrame`.  
  
 [Интерфейс ICorDebugILFrame3](icordebugilframe3-interface.md)\
 Предоставляет метод, инкапсулирующий возвращаемое значение функции.  
  
 [Интерфейс ICorDebugILFrame4](icordebugilframe4-interface.md)\
 Предоставляет методы, обеспечивающие доступ к локальным переменным и коду в кадре стека кода промежуточного языка. Параметр показывает, имеет ли отладчик доступ к переменным и коду, добавленным в инструментарий ReJIT профилировщика.  
  
 [Интерфейс ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)\
 Представляет сведения отладочного символа для поля экземпляра. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugInternalFrame](icordebuginternalframe-interface.md)\
 Задает типы кадров для отладчика.  
  
 [Интерфейс ICorDebugInternalFrame2](icordebuginternalframe2-interface.md)\
 Предоставляет сведения о внутренних кадрах, включая адрес стека и расположение по отношению к объектам [ICorDebugFrame](icordebugframe-interface.md) .  
  
 [Интерфейс Икордебуглоадедмодуле](icordebugloadedmodule-interface.md)\
 Предоставляет сведения о загруженном модуле. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)\
 Предоставляет методы для обработки обратных вызовов отладчика.  
  
 [Интерфейс ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md)\
 Предоставляет методы для поддержки обработки исключений отладчика и управляемых помощников по отладке (MDA). Интерфейс `ICorDebugManagedCallback2` является логическим расширением интерфейса `ICorDebugManagedCallback`.  
  
 [Интерфейс ICorDebugManagedCallback3](icordebugmanagedcallback3-interface.md)\
 Предоставляет метод обратного вызова, указывающий, что создано включенное пользовательское уведомление отладчика.  
  
 [Интерфейс ICorDebugMDA](icordebugmda-interface.md)\
 Представляет сообщение управляемого помощника по отладке (MDA).  
  
 [Интерфейс Икордебугмеморибуффер](icordebugmemorybuffer-interface.md)\
 Представляет буфер в памяти. **Доступен только в .NET Native.**  
  
 [Интерфейс Икордебугмержедассемблирекорд](icordebugmergedassemblyrecord-interface.md)\
 Предоставляет сведения о сборке после слияния. **Доступен только в .NET Native.**  
  
 [Интерфейс Икордебугметадаталокатор](icordebugmetadatalocator-interface.md)\
 Предоставляет сведения о метаданных для отладчика.  
  
 [Интерфейс ICorDebugModule](icordebugmodule-interface.md)\
 Представляет модуль среды CLR, который является либо исполняемым файлом, либо библиотекой динамической компоновки (DLL).  
  
 [Интерфейс ICorDebugModule2](icordebugmodule2-interface.md)\
 Служит логическим расширением интерфейса `ICorDebugModule`.  
  
 [Интерфейс метод icordebugmodule3](icordebugmodule3-interface.md)\
 Создает средство чтения символов для динамического модуля.  
  
 [Интерфейс Икордебугмодулебреакпоинт](icordebugmodulebreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для предоставления доступа к указанным модулям.  
  
 [Интерфейс Икордебугмодуледебужевент](icordebugmoduledebugevent-interface.md)\
 Расширяет интерфейс [ICorDebugDebugEvent](icordebugdebugevent-interface.md) для поддержки событий уровня модуля. **Доступен только в .NET Native.**  
  
 [Интерфейс Икордебугмодулинум](icordebugmoduleenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugModule`.  
  
 [Интерфейс Икордебугмутабледататаржет](icordebugmutabledatatarget-interface.md)\
 Расширяет интерфейс [ICorDebugDataTarget](icordebugdatatarget-interface.md) для поддержки целевых объектов данных.  
  
 [Интерфейс ICorDebugNativeFrame](icordebugnativeframe-interface.md)\
 Специализированная реализация интерфейса `ICorDebugFrame`, используемая для кадров машинного кода.  
  
 [Интерфейс ICorDebugNativeFrame2](icordebugnativeframe2-interface.md)\
 Предоставляет методы, проверяющие для кадров наличие взаимоотношений типа "дочерний-родительский".  
  
 [Интерфейс Икордебугобжектенум](icordebugobjectenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов объектов по их относительным виртуальным адресам (RVA).  
  
 [Интерфейс ICorDebugObjectValue](icordebugobjectvalue-interface.md)\
 Подкласс `ICorDebugValue`, представляющий значение, содержащее объект.  
  
 [Интерфейс ICorDebugObjectValue2](icordebugobjectvalue2-interface.md)\
 Расширяет интерфейс `ICorDebugObjectValue` для поддержки наследования и переопределений.  
  
 [Интерфейс ICorDebugProcess](icordebugprocess-interface.md)\
 Представляет процесс, выполняющий управляемый код.  
  
 [Интерфейс ICorDebugProcess2](icordebugprocess2-interface1.md)\
 Логическое расширение интерфейса `ICorDebugProcess`.  
  
 [Интерфейс ICorDebugProcess3](icordebugprocess3-interface.md)\
 Управляет пользовательскими уведомлениями отладчика.

 [Интерфейс ICorDebugProcess4](icordebugprocess4-interface.md)\
 Обеспечивает поддержку управления выполнением в процессе.
  
 [Интерфейс метод ICorDebugProcess5](icordebugprocess5-interface.md)\
 Расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) для поддержки доступа к управляемой куче, предоставляет сведения о сборке мусора управляемых объектов и определяет, загружает ли отладчик изображения из локального кэша образов в машинном код.  
  
 [Интерфейс ICorDebugProcess6](icordebugprocess6-interface.md)\
 Логически расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) , позволяя выполнять такие функции, как декодирование управляемых событий отладки, которые кодируются в событиях отладки машинного кода и разбиении виртуального модуля. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugProcess7](icordebugprocess7-interface.md)\
 Предоставляет метод, который настраивает отладчик для обработки обновлений находящихся в памяти метаданных в целевом процессе.  
  
 [Интерфейс ICorDebugProcess8](icordebugprocess8-interface.md)\
 Логически расширяет интерфейс [ICorDebugProcess](icordebugprocess-interface.md) , чтобы включать или отключать определенные типы обратных вызовов исключений [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) .  
  
 [Интерфейс Икордебугпроцессенум](icordebugprocessenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugProcess`.  
  
 [Интерфейс ICorDebugReferenceValue](icordebugreferencevalue-interface.md)\
 Подкласс интерфейса `ICorDebugValue`, поддерживающего ссылочные типы.  
  
 [Интерфейс ICorDebugRegisterSet](icordebugregisterset-interface.md)\
 Представляет набор регистров, доступных для компьютера, на котором в данный момент выполняется код.  
  
 [Интерфейс ICorDebugRegisterSet2](icordebugregisterset2-interface.md)\
 Расширяет возможности интерфейса `ICorDebugRegisterSet` для аппаратных платформ, количество регистров которых превышает 64.  
  
 [Интерфейс метод icordebugremote](icordebugremote-interface.md)\
 Позволяет запускать или подключать управляемый отладчик к удаленному целевому процессу.  
  
 [Интерфейс ICorDebugRemoteTarget](icordebugremotetarget-interface.md)\
 Предоставляет методы, позволяющие отлаживать приложения на основе Silverlight в среде CLR.  
  
 [Интерфейс Икордебугрунтимеунвиндаблефраме](icordebugruntimeunwindableframe-interface.md)\
 Предоставляет поддержку для неуправляемых методов, которым требуется среда CLR для раскручивания кадра.  
  
 [Интерфейс Икордебугстакквалк](icordebugstackwalk-interface.md)\
 Обеспечивает методы для получения управляемых методов или кадров в стеке потока.  
  
 [Интерфейс Икордебугстатикфиелдсимбол](icordebugstaticfieldsymbol-interface.md)\
 Представляет сведения символа отладки для статического поля. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugStepper](icordebugstepper-interface.md)\
 Представляет предпринимаемый отладчиком шаг при выполнении кода, служащий идентификатором на промежутке между подачей команды и ее завершением, а также предоставляет возможность отмены шага.  
  
 [Интерфейс ICorDebugStepper2](icordebugstepper2-interface1.md)\
 Предоставляет поддержку отладки "Только мой код".  
  
 [Интерфейс Икордебугстепперенум](icordebugstepperenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugStepper`.  
  
 [Интерфейс ICorDebugStringValue](icordebugstringvalue-interface.md)\
 Подкласс `ICorDebugHeapValue`, применяемый к строковым значениям.  
  
 [Интерфейс метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md)\
 Предоставляет методы, которые могут использоваться для получения сведений об отладочных символах. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugSymbolProvider2](icordebugsymbolprovider2-interface.md)\
 Логически расширяет интерфейс [метод icordebugsymbolprovider](icordebugsymbolprovider-interface.md) для получения дополнительных сведений об отладочных символах. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugThread](icordebugthread-interface.md)\
 Представляет поток в процессе. Время существования экземпляра `ICorDebugThread` равно времени существования потока, который он представляет.  
  
 [Интерфейс ICorDebugThread2](icordebugthread2-interface.md)\
 Служит логическим расширением интерфейса `ICorDebugThread`.  
  
 [Интерфейс ICorDebugThread3](icordebugthread3-interface.md)\
 Предоставляет точку входа для [икордебугстакквалк](icordebugstackwalk-interface.md) и соответствующих интерфейсов.  
  
 [Интерфейс ICorDebugThread4](icordebugthread4-interface.md)\
 Предоставляет сведения о блокировке потока.  
  
 [Интерфейс Икордебугсреаденум](icordebugthreadenum-interface1.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugThread`.  
  
 [Интерфейс ICorDebugType](icordebugtype-interface.md)\
 Представляет тип, который может быть базовым или сложным (иными словами, пользовательским). Если тип универсален, интерфейс `ICorDebugType` представляет универсальный тип с экземплярами.  
  
 [Интерфейс ICorDebugType2](icordebugtype2-interface.md)\
 Расширяет интерфейс [ICorDebugType](icordebugtype-interface.md) для получения идентификатора типа базового типа или сложного (определяемого пользователем) типа.  
  
 [Интерфейс ICorDebugTypeEnum](icordebugtypeenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugType`.  
  
 [Интерфейс Икордебугунманажедкаллбакк](icordebugunmanagedcallback-interface.md)\
 Предоставляет уведомление о событиях машинного кода, которые не связаны непосредственно со средой CLR.  
  
 [ICorDebugValue](icordebugvalue-interface.md)\
 Представляет значение для записи или чтения в отлаживаемом процессе.  
  
 [ICorDebugValue2](icordebugvalue2-interface.md)\
 Расширяет интерфейс `ICorDebugValue` для предоставления поддержки интерфейса `ICorDebugType`.  
  
 [Интерфейс ICorDebugValue3](icordebugvalue3-interface.md)\
 Расширяет интерфейсы "ICorDebugValue" и "ICorDebugValue2", чтобы обеспечить поддержку массивов, размер которых превышает 2 ГБ.  
  
 [ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)\
 Расширяет интерфейс `ICorDebugBreakpoint` для обеспечения доступа к указанным значениям.  
  
 [ICorDebugValueEnum](icordebugvalueenum-interface.md)\
 Реализует методы `ICorDebugEnum` и выполняет перечисление массивов `ICorDebugValue`.  
  
 [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)\
 Представляет локальную переменную или аргумент функции.  
  
 [Интерфейс ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)\
 Предоставляет перечислитель для локальных переменных и аргументов в функции.  
  
 [Интерфейс ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md)\
 Извлекает сведения символа отладки для статического поля. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorDebugVirtualUnwinder](icordebugvirtualunwinder-interface.md)\
 Предоставляет методы, помогающие очистить стек. **Доступен только в .NET Native.**  
  
 [Интерфейс ICorPublish](icorpublish-interface.md)\
 Служит универсальным интерфейсом для процессов публикации.  
  
 [Интерфейс ICorPublishAppDomain](icorpublishappdomain-interface.md)\
 Представляет и предоставляет информацию о домене приложения.  
  
 [Интерфейс ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md)\
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishAppDomain`, существующих в процессе в данный момент.  
  
 [Интерфейс ICorPublishEnum](icorpublishenum-interface.md)\
 Служит абстрактной базой для перечислителей публикации.  
  
 [Интерфейс ICorPublishProcess](icorpublishprocess-interface.md)\
 Предоставляет методы, позволяющие получить доступ к сведениям о процессе.  
  
 [Интерфейс ICorPublishProcessEnum](icorpublishprocessenum-interface.md)\
 Предоставляет методы, выполняющие перебор коллекции объектов `ICorPublishProcess`.  

 [Интерфейс ИсосдаЦинтерфаце](isosdacinterface-interface.md)\
 Предоставляет вспомогательные методы для доступа к данным из `SOS` .

 [Интерфейс Иксклрдатамесоддефинитион](ixclrdatamethoddefinition-interface.md)\
 Предоставляет методы для запроса сведений об определении метода.

 [Интерфейс Иксклрдатамесодинстанце](ixclrdatamethodinstance-interface.md)\
 Предоставляет методы для запроса сведений об экземпляре метода.

 [Интерфейс Иксклрдатамодуле](ixclrdatamodule-interface.md)\
 Предоставляет методы для запроса сведений о загруженном модуле.

 [Интерфейс Иксклрдатапроцесс](ixclrdataprocess-interface.md)\
 Предоставляет методы для запроса сведений о процессе.
  
## <a name="related-sections"></a>См. также  

 [Коклассы отладки](debugging-coclasses.md)\
 [Отладка глобальных статических функций](debugging-global-static-functions.md)\
 [Перечисления отладки](debugging-enumerations.md)\
 [Структуры отладки](debugging-structures.md)\
