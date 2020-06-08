---
title: Устаревшие функции размещения CLR
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework 1.1, hosting global static functions
- global static functions [.NET Framework hosting], version 2.0
- .NET Framework 2.0, hosting global static functions
- hosting global static functions [.NET Framework], version 2.0
ms.assetid: 91fbbb35-e543-4814-b806-371cebae8c5a
ms.openlocfilehash: 083d0ff285abb4a99ad05c791bc504ff7f282c6a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504372"
---
# <a name="deprecated-clr-hosting-functions"></a>Устаревшие функции размещения CLR
В этом разделе описаны неуправляемые глобальные статические функции, которые использовались в предыдущих версиях API размещения.  
  
 За исключением функций инфраструктуры ( `_Cor*` функций), которые используются только .NET Framework, эти функции являются устаревшими в .NET Framework 4.  
  
## <a name="activation-functions"></a>Функции активации  
 [Функция ClrCreateManagedInstance](clrcreatemanagedinstance-function.md)  
 Не рекомендуется. Создает экземпляр указанного управляемого типа.  
  
 [Функция CoInitializeCor](coinitializecor-function.md)  
 Устаревшее. Чтобы инициализировать среду CLR, используйте либо [CorBindToRuntimeEx](corbindtoruntimeex-function.md) , либо [корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md).  
  
 [Функция CoInitializeEE](coinitializeee-function.md)  
 Не рекомендуется. Гарантирует, что подсистема выполнения среды CLR загружается в процесс. Используйте вместо этого метод [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .  
  
 [Функция CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)  
 Не рекомендуется. Загружает среду CLR в процесс с использованием сведений о версии, хранящихся в XML-файле.  
  
 [Функция CorBindToRuntime](corbindtoruntime-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загружать среду CLR в процесс.  
  
 [Функция CorBindToRuntimeByCfg](corbindtoruntimebycfg-function.md)  
 Не рекомендуется. Загружает среду CLR в процесс с использованием сведений о версии, считываемых из XML-файла.  
  
 [Функция CorBindToRuntimeEx](corbindtoruntimeex-function.md)  
 Не рекомендуется. Позволяет неуправляемым узлам загружать среду CLR в процесс и устанавливать флаги для указания поведения среды CLR.  
  
 [Функция CorBindToRuntimeHost](corbindtoruntimehost-function.md)  
 Не рекомендуется. Позволяет узлам загружать указанную версию среды CLR в процесс.  
  
 [Функция GetCORRequiredVersion](getcorrequiredversion-function.md)  
 Не рекомендуется. Возвращает требуемый номер версии среды CLR.  
  
 [Функция GetCORSystemDirectory](getcorsystemdirectory-function.md)  
 Не рекомендуется. Возвращает каталог установки CLR, который загружается в процесс.  
  
 [Функция GetRealProcAddress](getrealprocaddress-function.md)  
 Не рекомендуется. Возвращает адрес указанной функции, которая экспортируется из последней установленной версии среды CLR.  
  
 [Функция GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)  
 Не рекомендуется. Возвращает сведения о версии и каталоге о среде CLR, запрошенной приложением.  
  
## <a name="clr-version-functions"></a>Функции версий среды CLR  
 Функции в этом разделе возвращают версию среды CLR. они не активируют среду CLR.  
  
 [Функция GetCORVersion](getcorversion-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, которая выполняется в текущем процессе.  
  
 [Функция GetFileVersion](getfileversion-function.md)  
 Не рекомендуется. Возвращает сведения о версии среды CLR указанного файла, используя указанный буфер.  
  
 [Функция GetRequestedRuntimeVersion](getrequestedruntimeversion-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, запрошенной указанным приложением. Если эта версия не установлена, возвращает последнюю версию, установленную до запрошенной версии.  
  
 [Функция GetRequestedRuntimeVersionForCLSID](getrequestedruntimeversionforclsid-function.md)  
 Не рекомендуется. Возвращает соответствующую информацию о версии среды CLR для класса с указанным идентификатором CLSID.  
  
 [Функция GetVersionFromProcess](getversionfromprocess-function.md)  
 Не рекомендуется. Возвращает номер версии среды CLR, связанной с указанным обработчиком процесса.  
  
 [Функция LockClrVersion](lockclrversion-function.md)  
 Не рекомендуется. Позволяет узлу определить версию среды CLR, которая будет использоваться в процессе перед явной инициализацией среды CLR.  
  
## <a name="hosting-functions"></a>Функции размещения  
 [Функция CallFunctionShim](callfunctionshim-function.md)  
 Не рекомендуется. Вызывает функцию с указанным именем и параметрами в указанной библиотеке.  
  
 [Функция CoEEShutDownCOM](coeeshutdowncom-function.md)  
 Не рекомендуется. Выгружает сборку COM из процесса.  
  
 [Функция CorExitProcess](corexitprocess-function.md)  
 Не рекомендуется. Завершает текущий неуправляемый процесс.  
  
 [Функция CorLaunchApplication](corlaunchapplication-function.md)  
 Не рекомендуется. Запускает приложение по указанному сетевому пути, используя указанные манифесты и другие данные приложения.  
  
 [Функция CorMarkThreadInThreadPool](cormarkthreadinthreadpool-function.md)  
 Не рекомендуется. Помечает выполняющийся в данный момент поток пула потоков для выполнения управляемого кода. Начиная с версии .NET Framework 2,0 эта функция не действует. Он не является обязательным и может быть удален из кода.  
  
 [Функция CoUninitializeCor](couninitializecor-function.md)  
 Устаревшее. Среду CLR нельзя выгрузить из процесса.  
  
 [Функция CoUninitializeEE](couninitializeee-function.md)  
 Устаревшее.  
  
 [Функция CreateDebuggingInterfaceFromVersion](createdebugginginterfacefromversion-function.md)  
 Не рекомендуется. Создает объект [ICorDebug](../debugging/icordebug-interface.md) на основе указанных сведений о версии.  
  
 [Функция CreateICeeFileGen](createiceefilegen-function.md)  
 Не рекомендуется. Создает объект [ицеефилежен](iceefilegen-class.md) .  
  
 [Функция DestroyICeeFileGen](destroyiceefilegen-function.md)  
 Не рекомендуется. Уничтожает объект [ицеефилежен](iceefilegen-class.md) .  
  
 [Указатель функции FExecuteInAppDomainCallback](fexecuteinappdomaincallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которую CLR вызывает для выполнения управляемого кода.  
  
 [Указатель функции FLockClrVersionCallback](flockclrversioncallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая вызывается средой CLR для уведомления узла о том, что инициализация запущена или завершена.  
  
 [Функция GetCLRIdentityManager](getclridentitymanager-function.md)  
 Не рекомендуется. Возвращает указатель на интерфейс, который позволяет среде CLR управлять удостоверениями.  
  
 [Функция LoadLibraryShim](loadlibraryshim-function.md)  
 Не рекомендуется. Загружает указанную версию .NET Framework DLL.  
  
 [Функция LoadStringRC](loadstringrc-function.md)  
 Не рекомендуется. Преобразует значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.  
  
 [Функция LoadStringRCEx](loadstringrcex-function.md)  
 Не рекомендуется. Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 [Указатель функции LPOVERLAPPED_COMPLETION_ROUTINE](lpoverlapped-completion-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел при завершении перекрытия (асинхронного) ввода-вывода на устройство.  
  
 [Указатель функции LPTHREAD_START_ROUTINE](lpthread-start-routine-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел о начале выполнения потока.  
  
 [Функция RunDll32ShimW](rundll32shimw-function.md)  
 Не рекомендуется. Выполняет указанную команду.  
  
 [Указатель функции WAITORTIMERCALLBACK](waitortimercallback-function-pointer.md)  
 Не рекомендуется. Указывает на функцию, которая уведомляет узел о том, что дескриптор ожидания имеет сигнал или время ожидания истекло.  
  
## <a name="infrastructure-functions"></a>Функции инфраструктуры  
 Функции в этом разделе предназначены для использования только .NET Framework.  
  
 [Функция _CorDllMain](cordllmain-function.md)  
 Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR сборки DLL и начинает выполнение.  
  
 [Функция _CorExeMain](corexemain-function.md)  
 Инициализирует среду CLR, находит управляемую точку входа в заголовке CLR исполняемой сборки и начинает выполнение.  
  
 [Функция _CorExeMain2](corexemain2-function.md)  
 Выполняет точку входа в указанном коде, сопоставленном с памятью. Эта функция вызывается загрузчиком операционной системы.  
  
 [Функция _CorImageUnloading](corimageunloading-function.md)  
 Уведомляет загрузчик об выгрузке образов управляемого модуля.  
  
 [Функция _CorValidateImage](corvalidateimage-function.md)  
 Проверяет образы управляемого модуля и уведомляет загрузчик операционной системы после их загрузки.  
  
## <a name="see-also"></a>См. также

- [Глобальные статические функции размещения платформы .NET Framework 4](net-framework-4-hosting-global-static-functions.md)
