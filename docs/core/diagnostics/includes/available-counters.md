---
ms.openlocfilehash: f561550d57e98a515fa3bdf56eea1dc1759b4e69
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024975"
---
## <a name="available-counters"></a>Доступные счетчики

В различных пакетах .NET основные метрики по сборке мусора, JIT-компиляции, сборкам, исключениям, потокам, сетям и веб-запросам публикуются с помощью EventCounters.

### <a name="systemruntime-counters"></a>Счетчики "System.Runtime"

Следующие счетчики публикуются как часть среды выполнения .NET и поддерживаются в [`RuntimeEventSource.cs`](https://github.com/dotnet/coreclr/blob/master/src/System.Private.CoreLib/src/System/Diagnostics/Eventing/RuntimeEventSource.cs).

| Счетчик | Описание |
|--|--|
| :::no-loc text="% Time in GC since last GC"::: (`time-in-gc`) | Процент времени в сборке мусора с момента последнего сборки мусора |
| :::no-loc text="Allocation Rate"::: (`alloc-rate`) | Скорость выделения в байтах |
| :::no-loc text="CPU Usage"::: (`cpu-usage`) | Процент использования ЦП |
| :::no-loc text="Exception Count"::: (`exception-count`) | Количество произошедших исключений |
| :::no-loc text="GC Heap Size"::: (`gc-heap-size`) | Количество байтов, которое должно быть выделено на основе <xref:System.GC.GetTotalMemory(System.Boolean)?displayProperty=nameWithType> |
| :::no-loc text="Gen 0 GC Count"::: (`gen-0-gc-count`) | Количество сборок мусора для поколения 0 |
| :::no-loc text="Gen 0 Size"::: (`gen-0-size`) | Количество байтов для сборки мусора поколения 0 |
| :::no-loc text="Gen 1 GC Count"::: (`gen-1-gc-count`) | Количество сборок мусора для поколения 1 |
| :::no-loc text="Gen 1 Size"::: (`gen-1-size`) | Количество байтов для сборки мусора поколения 1 |
| :::no-loc text="Gen 2 GC Count"::: (`gen-2-gc-count`) | Количество сборок мусора для поколения 2 |
| :::no-loc text="Gen 2 Size"::: (`gen-2-size`) | Количество байтов для сборки мусора поколения 2 |
| :::no-loc text="LOH Size"::: (`loh-size`) | Количество байтов для сборки мусора поколения 3 |
| :::no-loc text="Monitor Lock Contention Count"::: (`monitor-lock-contention-count`) | Значение, указывающее, сколько раз возникало состязание при попытке установить блокировку монитора на основе <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType> |
| :::no-loc text="Number of Active Timers"::: (`active-timer-count`) | Количество активных в данных момент экземпляров <xref:System.Threading.Timer> на основе <xref:System.Threading.Timer.ActiveCount?displayProperty=nameWithType> |
| :::no-loc text="Number of Assemblies Loaded"::: (`assembly-count`) | Количество экземпляров <xref:System.Reflection.Assembly>, загруженных в процесс в определенный момент времени |
| :::no-loc text="ThreadPool Completed Work Item Count"::: (`threadpool-completed-items-count`) | Количество рабочих элементов, обработанных на данный момент в <xref:System.Threading.ThreadPool> |
| :::no-loc text="ThreadPool Queue Length"::: (`threadpool-queue-length`) | Количество рабочих элементов, находящихся в настоящее время в очереди на обработку в <xref:System.Threading.ThreadPool> |
| :::no-loc text="ThreadPool Thread Count"::: (`threadpool-thread-count`) | Текущее количество потоков пула потоков в <xref:System.Threading.ThreadPool> на основе <xref:System.Threading.ThreadPool.ThreadCount?displayProperty=nameWithType> |
| :::no-loc text="Working Set"::: (`working-set`) | Объем физической памяти, сопоставленной контексту процесса, в определенный момент времени на основе <xref:System.Environment.WorkingSet?displayProperty=nameWithType> |

### <a name="microsoftaspnetcorehosting-counters"></a>Счетчики "Microsoft.AspNetCore.Hosting"

Следующие счетчики публикуются как часть [ASP.NET Core](/aspnet/core) и поддерживаются в [`HostingEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Hosting/Hosting/src/Internal/HostingEventSource.cs).

| Счетчик | Описание |
|--|--|
| :::no-loc text="Current Requests"::: (`current-requests`) | Общее количество запросов, которые были запущены, но еще не остановлены |
| :::no-loc text="Failed Requests"::: (`failed-requests`) | Общее число неудачных запросов, произошедших за время существования приложения |
| :::no-loc text="Request Rate"::: (`requests-per-second`) | Число запросов, выполняемых в секунду |
| :::no-loc text="Total Requests"::: (`total-requests`) | Общее число запросов, произошедших за время существования приложения |

### <a name="microsoftaspnetcorehttpconnections-counters"></a>Счетчики "Microsoft.AspNetCore.Http.Connections"

Следующие счетчики публикуются как часть [ASP.NET Core SignalR](/aspnet/core/signalr/introduction) и поддерживаются в [`HttpConnectionsEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/SignalR/common/Http.Connections/src/Internal/HttpConnectionsEventSource.cs).

| Счетчик | Описание |
|--|--|
| :::no-loc text="Average Connection Duration"::: (`connections-duration`) | Средняя продолжительность подключения в миллисекундах |
| :::no-loc text="Current Connections"::: (`current-connections`) | Количество активных подключений, которые были запущены, но еще не остановлены |
| :::no-loc text="Total Connections Started"::: (`connections-started`) | Общее число запущенных подключений |
| :::no-loc text="Total Connections Stopped"::: (`connections-stopped`) | Общее число остановленных подключений |
| :::no-loc text="Total Connections Timed Out"::: (`connections-timed-out`) | Общее число подключений, для которых истекло время ожидания |

### <a name="microsoft-aspnetcore-server-kestrel-counters"></a>Счетчики "Microsoft-AspNetCore-Server-Kestrel"

Следующие счетчики публикуются как часть [веб-сервера Kestrel ASP.NET Core](/aspnet/core/fundamentals/servers/kestrel) и поддерживаются в [`KestrelEventSource.cs`](https://github.com/dotnet/aspnetcore/blob/master/src/Servers/Kestrel/Core/src/Internal/Infrastructure/KestrelEventSource.cs).

| Счетчик | Описание |
|--|--|
| :::no-loc text="Connection Queue Length"::: (`connection-queue-length`) | Текущая длина очереди подключения |
| :::no-loc text="Connection Rate"::: (`connections-per-second`) | Количество подключений к веб-серверу в секунду |
| :::no-loc text="Current Connections"::: (`current-connections`) | Текущее количество активных подключений к веб-серверу |
| :::no-loc text="Current TLS Handshakes"::: (`current-tls-handshakes`) | Текущее количество подтверждений TLS |
| :::no-loc text="Current Upgraded Requests (WebSockets)"::: (`current-upgraded-requests`) | Текущее количество обновленных запросов (WebSockets) |
| :::no-loc text="Failed TLS Handshakes"::: (`failed-tls-handshakes`) | Общее число неудачных подтверждений TLS |
| :::no-loc text="Request Queue Length"::: (`request-queue-length`) | Текущая длина очереди запросов |
| :::no-loc text="TLS Handshake Rate"::: (`tls-handshakes-per-second`) | Количество подтверждений TLS в секунду |
| :::no-loc text="Total Connections"::: (`total-connections`) | Общее число подключений к веб-серверу |
| :::no-loc text="Total TLS Handshakes"::: (`total-tls-handshakes`) | Общее число подтверждений TLS на веб-сервере |
