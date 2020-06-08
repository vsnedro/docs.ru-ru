---
title: Размещение перечислений
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged enumerations [.NET Framework], hosting
- enumerations [.NET Framework hosting]
- hosting enumerations [.NET Framework]
ms.assetid: e09131eb-1f7d-4f52-ae42-7393e9b62ef6
ms.openlocfilehash: 8edace3191ee4477b19f199d5db6c891c993dcd5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504307"
---
# <a name="hosting-enumerations"></a>Размещение перечислений
В этом разделе описаны неуправляемые перечисления, используемые API размещения.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Перечисление CLSID_RESOLUTION_FLAGS](clsid-resolution-flags-enumeration.md)  
 Содержит значения, которые указывают, как общеязыковая среда выполнения (CLR) должна разрешать `CLSID` .  
  
 [Перечисление COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md)  
 Указывает статистику, записываемую для сборки мусора.  
  
 [Перечисление COR_GC_THREAD_STATS_TYPES](cor-gc-thread-stats-types-enumeration.md)  
 Указывает статистику сборки мусора для потока.  
  
 [Перечисление EApiCategories](eapicategories-enumeration.md)  
 Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенном коде.  
  
 [Перечисление EBindPolicyLevels](ebindpolicylevels-enumeration.md)  
 Предоставляет флаги, указывающие уровень применения или изменения политики сборки.  
  
 [Перечисление ECLRAssemblyIdentityFlags](eclrassemblyidentityflags-enumeration.md)  
 Указывает тип удостоверения сборки.  
  
 [Перечисление EClrEvent](eclrevent-enumeration.md)  
 Описывает события CLR, для которых узел может регистрировать обратные вызовы.  
  
 [Перечисление EClrFailure](eclrfailure-enumeration.md)  
 Описывает набор сбоев, для которых узел может задавать действия политики.  
  
 [Перечисление EClrOperation](eclroperation-enumeration.md)  
 Описывает набор операций, для которых узел может применять действия политики.  
  
 [Перечисление EClrUnhandledException](eclrunhandledexception-enumeration.md)  
 Описывает доступные параметры для управления исключениями, которые не обрабатываются в пользовательском коде.  
  
 [Перечисление EContextType](econtexttype-enumeration.md)  
 Описывает контекст безопасности выполняющегося в данный момент потока.  
  
 [Перечисление ECustomDumpFlavor](ecustomdumpflavor-enumeration.md)  
 Содержит значения, указывающие, какие элементы следует включать в пользовательское подмножество дампа кучи при сообщении об ошибках.  
  
 [Перечисление ECustomDumpItemKind](ecustomdumpitemkind-enumeration.md)  
 Зарезервировано для будущего расширения структуры [структуры кустомдумпитем](customdumpitem-structure.md) .  
  
 [Перечисление EHostApplicationPolicy](ehostapplicationpolicy-enumeration.md)  
 Указывает, как изменить объект интерфейса [интерфейса IHostAssemblyManager](ihostassemblymanager-interface.md) . Это перечисление является устаревшим.  
  
 [Перечисление EHostBindingPolicyModifyFlags](ehostbindingpolicymodifyflags-enumeration.md)  
 Позволяет узлу указать тип перенаправления, которое должна выполнять среда CLR при применении изменений политики из исходной сборки к целевой сборке.  
  
 [Перечисление EInitializeNewDomainFlags](einitializenewdomainflags-enumeration.md)  
 Позволяет узлу предоставлять среде выполнения сведения об инициализации домена приложения.  
  
 [Перечисление EMemoryAvailable](ememoryavailable-enumeration.md)  
 Содержит значения, указывающие объем свободной физической памяти на компьютере.  
  
 [Перечисление EMemoryCriticalLevel](ememorycriticallevel-enumeration.md)  
 Содержит значения, которые указывают на влияние сбоя при запросе определенного выделения памяти, но не могут быть удовлетворены.  
  
 [Перечисление EPolicyAction](epolicyaction-enumeration.md)  
 Описывает действия политики, которые узел может задать для операций, описанных в разделе Перечисление [еклроператион](eclroperation-enumeration.md) и сбои, описанные в разделе [перечисление еклрфаилуре](eclrfailure-enumeration.md).  
  
 [Перечисление ESymbolReadingPolicy](esymbolreadingpolicy-enumeration.md)  
 Содержит значения, задают политику чтения PDB-файлов.  
  
 [Перечисление ETaskType](etasktype-enumeration.md)  
 Содержит значения, указывающие тип задачи, представленной [интерфейсом ICLRTask](iclrtask-interface.md) или интерфейсом [IHostTask](ihosttask-interface.md) .  
  
 [Перечисление HOST_TYPE](host-type-enumeration.md)  
 Содержит значения, указывающие тип узла, запускающего приложение.  
  
 [MALLOC_TYPE - перечисление](malloc-type-enumeration.md)  
 Содержит значения, указывающие характеристики выделяемой памяти.  
  
 [Перечисление METAHOST_CONFIG_FLAGS](metahost-config-flags-enumeration.md)  
 Описывает возможные флаги, возвращаемые в `pdwConfigFlags` параметре метода [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) .  
  
 [Перечисление METAHOST_POLICY_FLAGS](metahost-policy-flags-enumeration.md)  
 Предоставляет политики привязки, которые являются общими для большинства хостов среды выполнения.  
  
 [Перечисление RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md)  
 Содержит значения, которые указывают, какие сведения о среде CLR должны возвращаться.  
  
 [Перечисление StackOverflowType](stackoverflowtype-enumeration.md)  
 Содержит значения, указывающие основную причину события переполнения стека.  
  
 [Перечисление STARTUP_FLAGS](startup-flags-enumeration.md)  
 Содержит значения, которые указывают на поведение среды CLR при запуске.  
  
 [Перечисление ValidatorFlags](validatorflags-enumeration.md)  
 Содержит значения, указывающие тип проверки, которая должна быть выполнена при вызове [метода Validate](iclrvalidator-validate-method.md).  
  
 [Перечисление WAIT_OPTION](wait-option-enumeration.md)  
 Указывает действие, которое должен выполнить узел при выполнении операции, запрошенной блоками CLR.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Размещение коклассов](hosting-coclasses.md)  
  
 [Интерфейсы размещения](hosting-interfaces.md)  
  
 [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)  
  
 [Структуры размещения](hosting-structures.md)
