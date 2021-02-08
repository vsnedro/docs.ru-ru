---
description: 'Дополнительные сведения: отладка Silverlight'
title: Отладка в Silverlight
ms.date: 03/30/2017
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
ms.assetid: 5e903e04-17d0-4014-ac9a-a43330ec8b1c
ms.openlocfilehash: 54a3f7f4b2de867509ff94dafa25c067a78b3ee6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800543"
---
# <a name="silverlight-debugging"></a>Отладка в Silverlight

В этом разделе описываются среда и интерфейсы, предоставляемые средой CLR для поддержки отладки приложений на основе Silverlight, работающих в ОС Windows или на платформе Macintosh.  
  
## <a name="in-this-section"></a>В этом разделе  

 [Функция EnumerateCLRs](enumerateclrs-function.md)  
 Предоставляет механизм для перечисления сред CLR в процессе.  
  
 [Функция CloseCLREnumeration](closeclrenumeration-function.md)  
 Закрывает все допустимые события продолжения запуска среды CLR, расположенные в массиве дескрипторов, возвращенных [функцией EnumerateCLRs](enumerateclrs-function.md), и освобождает память для массивов дескрипторов и строк.  
  
 [Функция CreateCoreClrDebugTarget](createcoreclrdebugtarget-function.md)  
 Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
 [Функция CreateCordbObject](createcordbobject-function.md)  
 Создает интерфейс отладчика, обеспечивающий функциональность для создания управляемого сеанса отладки в удаленном процессе.  
  
 [Функция CreateVersionStringFromModule](createversionstringfrommodule-function.md)  
 Создает строку версии из пути среды CLR в целевом процессе.  
  
 [Функция CreateDebuggingInterfaceFromVersion](createdebugginginterfacefromversion-function-for-silverlight.md)  
 Принимает строку версии среды CLR, возвращаемую функцией [CreateVersionStringFromModule Function](createversionstringfrommodule-function.md), и возвращает соответствующий интерфейс отладчика.  
  
 [Структура CoreClrDebugProcInfo](coreclrdebugprocinfo-structure.md)  
 Представляет процесс, который выполняется на удаленном компьютере.  
  
 [Структура CoreClrDebugRuntimeInfo](coreclrdebugruntimeinfo-structure.md)  
 Представляет экземпляр среды CLR, который загружается в процессе на удаленном компьютере.  
  
 [Функция GetStartupNotificationEvent](getstartupnotificationevent-function.md)  
 Создает или открывает обработчик событий, который будет информироваться любой средой CLR, загружаемой в указанный целевой процесс.  
  
 [Интерфейс ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)  
 Создает подключение к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
 [Функция InitDbgTransportManager](initdbgtransportmanager-function.md)  
 Инициализирует диспетчер транспорта для подключения к удаленному целевому объекту для процесса и перечисления среды выполнения.  
  
 [Функция ShutdownDbgTransportManager](shutdowndbgtransportmanager-function.md)  
 Завершает работу диспетчера транспорта для подключения к удаленному целевому компьютеру.  
  
## <a name="see-also"></a>См. также

- [Компонентные классы отладки](debugging-coclasses.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Глобальные статические функции отладки](debugging-global-static-functions.md)
- [Перечисления отладки](debugging-enumerations.md)
- [Структуры отладки](debugging-structures.md)
