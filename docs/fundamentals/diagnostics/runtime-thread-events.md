---
title: События среды выполнения ThreadPool
description: См. раздел События пула потоков среды выполнения .NET, собирающий диагностические сведения о пуле потоков в .NET Core. События пула потоков — это события пула рабочих потоков или события пула потоков ввода-вывода.
ms.date: 11/13/2020
ms.topic: reference
helpviewer_keywords:
- ThreadPool events (CoreCLR)
- ETW, thread pool events (CoreCLR)
ms.openlocfilehash: cdd6041c5842d4922c60e33daf6db366f7d35327
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96594122"
---
# <a name="net-runtime-thread-pool-events"></a>События пула потоков среды выполнения .NET

Эти события собираются сведения о рабочем процессе и потоках ввода-вывода в ThreadPool. Дополнительные сведения об использовании этих событий в целях диагностики см. в разделе [ведение журнала и трассировка приложений .NET](../../core/diagnostics/logging-tracing.md) .

## <a name="iothreadcreate_v1-event"></a>IOThreadCreate_V1 событие

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Условие вызова|
|-----------------------------------|-----------|
|`IOThreadCreate_V1`|44|Поток ввода-вывода создается в пуле потоков.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Число потоков ввода-вывода, включая вновь созданный поток.|
|`NumRetired`|`win:UInt64`|Число завершенных рабочих потоков.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="iothreadterminate_v1-event"></a>IOThreadTerminate_V1 событие

 В следующей таблице показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level
|-----------------------------------|-----------
|`ThreadingKeyword` (0x10000)|Информационный (4)

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Условие вызова|
|-----------|--------------|-----------------|
|`IOThreadTerminate`|45|Поток ввода-вывода завершается в пуле потоков.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Число потоков ввода-вывода, остающихся в пуле потоков.|
|`NumRetired`|`win:UInt64`|Число завершенных потоков ввода-вывода.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="iothreadretire_v1-event"></a>IOThreadRetire_V1 событие

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Условие вызова|
|-----------|--------------|-----------------|
|`IOThreadRetire_V1`|46|Поток ввода-вывода становится кандидатом на завершение.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Число потоков ввода-вывода, остающихся в пуле потоков.|
|`NumRetired`|`win:UInt64`|Число завершенных потоков ввода-вывода.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="iothreadunretire_v1-event"></a>IOThreadUnretire_V1 событие

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Условие вызова|
|-----------|--------------|-----------------|
|`IOThreadUnretire_V1`|47|Завершенный поток ввода-вывода повторно активируется из-за ввода-вывода, поступающего в течение периода ожидания после того, как поток стал кандидатом на завершение.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`Count`|`win:UInt64`|Число потоков ввода-вывода в пуле потоков, включая этот поток.|
|`NumRetired`|`win:UInt64`|Число завершенных потоков ввода-вывода.|
|`ClrInstanceID`|`Win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadstart-event"></a>Событие Среадпулворкерсреадстарт

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStart`|50|Создается рабочий поток.|

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, доступных для выполнения процесса, включая уже работающие потоки.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, которые недоступны для выполнения процесса, но находятся в резерве на случай, если позже понадобятся дополнительные потоки.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadstop-event"></a>Событие Среадпулворкерсреадстоп

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadStop`|51|Рабочий поток останавливается.|

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, доступных для выполнения процесса, включая уже работающие потоки.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, которые недоступны для выполнения процесса, но находятся в резерве на случай, если позже понадобятся дополнительные потоки.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadwait-event"></a>Событие Среадпулворкерсреадваит

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadWait`|57|Рабочий поток начинает ожидание работы.|

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, доступных для выполнения процесса, включая уже работающие потоки.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, которые недоступны для выполнения процесса, но находятся в резерве на случай, если позже понадобятся дополнительные потоки.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadretirementstart-event"></a>Событие Среадпулворкерсреадретирементстарт

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStart`|52|Рабочий поток завершается.|

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, доступных для выполнения процесса, включая уже работающие потоки.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, которые недоступны для выполнения процесса, но находятся в резерве на случай, если позже понадобятся дополнительные потоки.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadretirementstop-event"></a>Событие Среадпулворкерсреадретирементстоп

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadRetirementStop`|53|Завершенный рабочий поток снова становится активным.|

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ActiveWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, доступных для выполнения процесса, включая уже работающие потоки.|
|`RetiredWorkerThreadCount`|`win:UInt32`|Число рабочих потоков, которые недоступны для выполнения процесса, но находятся в резерве на случай, если позже понадобятся дополнительные потоки.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentsample-event"></a>Событие Среадпулворкерсреададжустментсампле

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentSample`|54|Указывает на сбор сведений для одного образца, то есть измерение пропускной способности с определенным уровнем параллелизма в некоторый момент времени.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`Throughput`|`win:Double`|Число завершений в единицу времени.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentadjustment-event"></a>Событие Среадпулворкерсреададжустментаджустмент

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentAdjustment`|55|Регистрирует изменение в управлении, когда алгоритм вставки потока (поиск экстремума) определяет, что произошло изменение уровня параллелизма.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`AverageThroughput`|`win:Double`|Средняя пропускная способность образца измерений.|
|`NewWorkerThreadCount`|`win:UInt32`|Новое число активных рабочих потоков.|
|`Reason`|`win:UInt32`|Причина корректировки:<br /><br /> `0x0` Прогрева.<br /><br /> `0x1` Инициализации.<br /><br /> `0x2` — Случайное перемещение.<br /><br /> `0x3` -Увеличиваться перемещение.<br /><br /> `0x4` — Точка изменения.<br /><br /> `0x5` Стабилизация.<br /><br /> `0x6` Перегрузка.<br /><br /> `0x7` -Истекло время ожидания потока.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolworkerthreadadjustmentstats-event"></a>Событие Среадпулворкерсреададжустментстатс

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Подробный (5)

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolWorkerThreadAdjustmentStats`|56|Собирает данные по пулу потоков.|

 В следующей таблице показаны данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`Duration`|`win:Double`|Время в секундах, в течение которого выполнялся сбор статистики.|
|`Throughput`|`win:Double`|Среднее число завершений в секунду в течение данного интервала.|
|`ThreadWave`|`win:Double`|Зарезервировано для внутреннего использования.|
|`ThroughputWave`|`win:Double`|Зарезервировано для внутреннего использования.|
|`ThroughputErrorEstimate`|`win:Double`|Зарезервировано для внутреннего использования.|
|`AverageThroughputErrorEstimate`|`win:Double`|Зарезервировано для внутреннего использования.|
|`ThroughputRatio`|`win:Double`|Относительное улучшение пропускной способности, вызванное изменениями числа активных рабочих потоков в течение этого интервала.|
|`Confidence`|`win:Double`|Мера обоснованности поля ThroughputRatio.|
|`NewcontrolSetting`|`win:Double`|Число активных рабочих потоков, которое будет служить основой для будущих изменений числа активных потоков.|
|`NewThreadWaveMagnitude`|`win:UInt16`|Величина будущих изменений числа активных потоков.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор экземпляра CLR или CoreCLR.|

## <a name="threadpoolenqueue-event"></a>Событие Среадпуленкуеуе

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Подробный (5)

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolEnqueue`|61|Рабочий элемент был поставлен в очередь пула потоков.|

 В следующей таблице показаны данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|Указатель на рабочий запрос.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор для экземпляра CoreCLR.|

## <a name="threadpooldequeue-event"></a>Событие Среадпулдекуеуе

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Подробный (5)

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolDequeue`|62|Рабочий элемент был удален из очереди пула потоков.|

 В следующей таблице показаны данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`WorkID`|`win:Pointer`|Указатель на рабочий запрос.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор для экземпляра CoreCLR.|

## <a name="threadpoolioenqueue-event"></a>Событие Среадпулиоенкуеуе

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Подробный (5)

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolIOEnqueue`|63|Поток помещает в очередь уведомление о завершении ввода-вывода после выполнения асинхронного ввода-вывода.|

 В следующей таблице показаны данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Зарезервировано для внутреннего использования.|
|`Overlapped`|`win:Pointer`|Зарезервировано для внутреннего использования.|
|`MultiDequeues`|`win:Boolean`|Зарезервировано для внутреннего использования.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор для экземпляра CoreCLR.|

## <a name="threadpooliodequeue-event"></a>Событие Среадпулиодекуеуе

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Подробный (5)

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolIODequeue`|64|Поток выставит в очередь уведомление о завершении ввода-вывода.|

 В следующей таблице показаны данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Зарезервировано для внутреннего использования.|
|`Overlapped`|`win:Pointer`|Зарезервировано для внутреннего использования.|
|`MultiDequeues`|`win:Boolean`|Зарезервировано для внутреннего использования.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор для экземпляра CoreCLR.|

## <a name="threadpooliopack-event"></a>Событие Среадпулиопакк

 В таблице ниже показаны ключевое слово и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Подробный (5)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|-----------|--------------|-----------------|
|`ThreadPoolIOPack`|65|Вызывается перекрытый пакет операций ввода-вывода с перекрытием ThreadPool.|

 В следующей таблице показаны данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`NativeOverlapped`|`win:Pointer`|Зарезервировано для внутреннего использования.|
|`Overlapped`|`win:Pointer`|Зарезервировано для внутреннего использования.|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор для экземпляра CoreCLR.|

## <a name="threadcreating-event"></a>Событие Среадкреатинг

 В следующей таблице показаны ключевые слова и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|----------------|---------------|-----------------|
|`ThreadCreating`|70|Поток создан.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|Идентификатор потока|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор для экземпляра CoreCLR.|

## <a name="threadrunning-event"></a>Событие Среадруннинг

 В следующей таблице показаны ключевые слова и уровень.

|Ключевое слово для вызова события|Level|
|-----------------------------------|-----------|
|`ThreadingKeyword` (0x10000)|Информационный (4)|

 В таблице ниже представлены сведения о событии.

|Событие|Идентификатор события|Описание|
|----------------|---------------|-----------------|
|`ThreadRunning`|71|Поток начал выполнение.|

 В таблице ниже представлены данные события.

|Имя поля|Тип данных|Описание|
|----------------|---------------|-----------------|
|`ID`|`win:Pointer`|Идентификатор потока|
|`ClrInstanceID`|`win:UInt16`|Уникальный идентификатор для экземпляра CoreCLR.|