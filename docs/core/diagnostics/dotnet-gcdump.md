---
title: Средство диагностики dotnet-gcdump — .NET CLI
description: Узнайте, как установить и использовать средство CLI dotnet-gcdump для сбора дампов сборщика мусора активных процессов .NET с помощью .NET EventPipe.
ms.date: 11/17/2020
ms.openlocfilehash: 59de1845ada9e5bdd0b24bf4312517283324ce94
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826044"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a>Средство анализа кучи (dotnet-gcdump)

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1 и более поздних версий

## <a name="install"></a>Установка

Есть два способа загрузки и установки `dotnet-gcdump`:

- **Средство dotnet global:**

  Чтобы установить последнюю версию [пакета NuGet](https://www.nuget.org/packages/dotnet-gcdump) `dotnet-gcdump`, используйте команду [dotnet tool install](../tools/dotnet-tool-install.md).

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- **Прямое скачивание:**

  скачайте исполняемый файл средства, соответствующий вашей платформе:

  | OS  | Платформа |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-gcdump/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64) |

## <a name="synopsis"></a>Краткий обзор

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a>Описание

Глобальное средство `dotnet-gcdump` собирает дампы сборщика мусора для активных процессов .NET с помощью [EventPipe](./eventpipe.md). Дампы сборщика мусора создаются путем его запуска в целевом процессе, включения специальных событий и повторного создания графа корней объектов из потока событий. Этот процесс позволяет собирать дампы сборщика мусора во время выполнения процесса и с минимальными издержками. Эти дампы могут быть полезны в нескольких сценариях.

- Сравнение количества объектов в куче в нескольких моментах времени.
- Анализ корней объектов (ответы на вопросы вида "что все еще содержит ссылку на этот тип?").
- Сбор общей статистики о количестве объектов в куче.

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a>Просмотр дампа сборщика мусора, захваченного с помощью dotnet-gcdump

В Windows файлы `.gcdump` можно просмотреть в [PerfView](https://github.com/microsoft/perfview) для анализа или в Visual Studio. В настоящее время невозможно открыть файлы `.gcdump` на платформах, отличных от Windows.

Вы можете объединить несколько файлов `.gcdump` и открыть их одновременно в Visual Studio, чтобы получить возможность сравнения.

## <a name="options"></a>Параметры

- **`--version`**

  Отображает версию программы `dotnet-gcdump`.

- **`-h|--help`**

  Отображение справки в командной строке.

## `dotnet-gcdump collect`

Собирает дамп сборщика мусора из выполняемого в данный момент процесса.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a>Параметры

- **`-h|--help`**

  Отображение справки в командной строке.

- **`-p|--process-id <pid>`**

  Идентификатор процесса, из которого нужно получить дамп сборщика мусора.

- **`-o|--output <gcdump-file-path>`**

  Путь, по которому нужно записывать собранные дампы сборщика мусора. Значение по умолчанию: *.\\ГГГГММДД\_ЧЧММСС\_\<pid>.gcdump*.

- **`-v|--verbose`**

  Выводить журнал во время сбора дампа сборщика мусора.

- **`-t|--timeout <timeout>`**

  Прервать сбор дампа сборщика мусора, если он занимает больше указанного количества секунд. Значение по умолчанию — 30.

- **`-n|--name <name>`**

  Имя процесса, из которого нужно получить дамп сборщика мусора.

## `dotnet-gcdump ps`

Список процессов dotnet, из которых можно получить дамп сборщика мусора.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

Создание отчета из ранее созданного дампа сборщика мусора или из выполняющегося процесса и запись его в `stdout`.

### <a name="synopsis"></a>Краткий обзор

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a>Параметры

- **`-h|--help`**

  Отображение справки в командной строке.

- **`-p|--process-id <pid>`**

  Идентификатор процесса, из которого нужно получить дамп сборщика мусора.

- **`-t|--report-type <HeapStat>`**

  Тип создаваемого отчета. Доступные значения: heapstat (по умолчанию).

## <a name="troubleshoot"></a>Диагностика

- В gcdump нет сведений о типе.

   До .NET Core 3.1 существовала проблема, при которой кэш типов не очищался между вызовами gcdump, когда они вызывались с помощью EventPipe. Это приводило к тому, что события, необходимые для определения сведений о типе, не отправлялись для второго и последующего вызовов gcdump. Это было исправлено в версии .NET Core 3.1-preview2.

- COM и статические типы не содержатся в дампе сборщика мусора.

   До .NET Core 3.1-preview2 существовала проблема, при которой COM и статические типы не отправлялись при вызове дампа сборщика мусора через EventPipe. Это было исправлено в версии .NET Core 3.1-preview2.
