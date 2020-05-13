---
title: Команда dotnet test
description: Команда dotnet test служит для выполнения модульных тестов в проекте.
ms.date: 04/29/2020
ms.openlocfilehash: ef71e48daa7c4a6f33961d05a2f3def122087b0e
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975437"
---
# <a name="dotnet-test"></a>dotnet test

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

## <a name="name"></a>name

`dotnet test` — драйвер тестов .NET, используемый для проведения модульных тестов.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet test [<PROJECT> | <SOLUTION> | <DIRECTORY> | <DLL>]
    [-a|--test-adapter-path <PATH_TO_ADAPTER>] [--blame]
    [-c|--configuration <CONFIGURATION>]
    [--collect <DATA_COLLECTOR_FRIENDLY_NAME>]
    [-d|--diag <PATH_TO_DIAGNOSTICS_FILE>] [-f|--framework <FRAMEWORK>]
    [--filter <EXPRESSION>] [--interactive]
    [-l|--logger <LOGGER_URI/FRIENDLY_NAME>] [--no-build]
    [--nologo] [--no-restore] [-o|--output <OUTPUT_DIRECTORY>]
    [-r|--results-directory <PATH>] [--runtime <RUNTIME_IDENTIFIER>]
    [-s|--settings <SETTINGS_FILE>] [-t|--list-tests]
    [-v|--verbosity <LEVEL>] [[--] <RunSettings arguments>]

dotnet test -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet test` служит для выполнения модульных тестов в решении. Команда `dotnet test` создает решение и запускает приложение тестового узла для каждого тестового проекта в решении. Тестовый узел выполняет тесты в заданном проекте с помощью платформы тестирования, например MSTest, NUnit или xUnit, и сообщает об успешном или неуспешном завершении каждого теста. Если все тесты выполнены успешно, средство выполнения тестов возвращает код 0. Если же любой тест завершается с ошибкой, средство выполнения возвращает 1.

Для проектов с несколькими целевыми платформами тесты запускаются для каждой из них. Тестовый узел и платформа модульных тестов упаковываются в пакеты NuGet и восстанавливаются как обычные зависимости проекта.

Тестовый проект указывает средство выполнения тестов с помощью обычного элемента `<PackageReference>`, как показано в следующем примере файла проекта:

[!code-xml[XUnit Basic Template](../../../samples/snippets/csharp/xunit-test/xunit-test.csproj)]

Где `Microsoft.NET.Test.Sdk` — это тестовый узел, `xunit` — платформа тестирования. `xunit.runner.visualstudio` — это адаптер теста, позволяющий платформе xUnit работать с тестовым узлом.

### <a name="implicit-restore"></a>Неявное восстановление

[!INCLUDE[dotnet restore note](~/includes/dotnet-restore-note.md)]

## <a name="arguments"></a>Аргументы

- **`PROJECT | SOLUTION | DIRECTORY | DLL`**

  - Путь к тестовому проекту.
  - Путь к решению.
  - Путь к каталогу, содержащему проект или решение.
  - Путь к *DLL-файлу* тестового проекта.

  Если он не указан, команда ищет проект или решение в текущем каталоге.

## <a name="options"></a>Параметры

- **`-a|--test-adapter-path <PATH_TO_ADAPTER>`**

  Путь к каталогу для поиска дополнительных адаптеров теста. Проверяются только *DLL*-файлы с суффиксом `.TestAdapter.dll`. Если не указано, выполняется поиск по каталогу тестового *DLL*.

- **`--blame`**

  Выполнение тестов в режиме обвинения. Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов. При обнаружении сбоя он создает файл последовательности в `TestResults/<Guid>/<Guid>_Sequence.xml`, который фиксирует порядок тестов, выполненных до сбоя.

- **`-c|--configuration <CONFIGURATION>`**

  Определяет конфигурацию сборки. Значение по умолчанию — `Debug`, но конфигурация проекта может переопределить этот параметр SDK по умолчанию.

- **`--collect <DATA_COLLECTOR_FRIENDLY_NAME>`**

  Включает сборщик данных для тестового запуска. Дополнительные сведения см. в разделе [Мониторинг и анализ тестового запуска](https://aka.ms/vstest-collect).

- **`-d|--diag <PATH_TO_DIAGNOSTICS_FILE>`**

  Включает режим диагностики для платформы тестирования и записывает диагностические сообщения в указанный файл и в файлы рядом с ним. Процесс, который заносит сообщения в журнал, определяет, какие файлы создаются, например `*.host_<date>.txt` для журнала тестового узла и `*.datacollector_<date>.txt` для журнала сборщика данных.

- **`-f|--framework <FRAMEWORK>`**

  Определяет принудительное использование `dotnet` или тестового узла .NET Framework для двоичных файлов теста. Этот параметр определяет только используемый тип узла. Реальная используемая версия платформы определяется в файле *runtimeconfig.json* тестового проекта. Если этот параметр не указан, для определения типа узла используется [атрибут сборки TargetFramework](/dotnet/api/system.runtime.versioning.targetframeworkattribute). Если этот атрибут удален из *DLL*, используется узел .NET Framework.

- **`--filter <EXPRESSION>`**

  Фильтрует тесты в текущем проекте с помощью заданного выражения. Дополнительные сведения см. в разделе [Сведения о параметре "Фильтр"](#filter-option-details). Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).

- **`-h|--help`**

  Выводит краткую справку по команде.

- **`--interactive`**

  Позволяет команде остановиться и дождаться, пока пользователь выполнит действие или введет данные. Например, чтобы завершить проверку подлинности. Доступно, начиная с пакета SDK для .NET Core 3.0.

- **`-l|--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Указывает средство ведения журнала для результатов тестирования. В отличие от MSBuild, dotnet test не принимает аббревиатуры: вместо `-l "console;v=d"` используйте `-l "console;verbosity=detailed"`.

- **`--no-build`**

  Не выполняет сборку тестового проекта перед запуском. Он также неявно задает флаг `--no-restore`.

- **`--nologo`**

  Запуск тестов без отображения баннера TestPlatform Майкрософт. Доступно, начиная с пакета SDK для .NET Core 3.0.

- **`--no-restore`**

  Не выполняет неявное восстановление при выполнении команды.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Каталог, в котором выполняется поиск двоичных файлов для выполнения. Если значение не указано, путь по умолчанию — `./bin/<configuration>/<framework>/`.  Для проектов с несколькими целевыми платформами (с помощью свойства `TargetFrameworks`) необходимо также определить `--framework` при указании этого параметра. `dotnet test` всегда запускает тесты из выходного каталога. Для использования ресурсов тестирования в выходном каталоге можно использовать <xref:System.AppDomain.BaseDirectory%2A?displayProperty=nameWithType>.

- **`-r|--results-directory <PATH>`**

  Каталог для сохранения результатов тестов. Если указанный каталог не существует, он создается. По умолчанию используется `TestResults` в каталоге, содержащем файл проекта.

- **`--runtime <RUNTIME_IDENTIFIER>`**

  Целевая среда выполнения для тестирования.

- **`-s|--settings <SETTINGS_FILE>`**

  Файл `.runsettings`, который необходимо использовать для проведения тестов. Обратите внимание, что элемент `TargetPlatform` (x86|x64) не влияет на `dotnet test`. Чтобы запускать тесты для x86, установите версию .NET Core x86. Разрядность *dotnet.exe* в пути будет использоваться для выполнения тестов. Дополнительные сведения см. в следующих ресурсах:

  - [Настройка модульных тестов с помощью файла `.runsettings`.](/visualstudio/test/configure-unit-tests-by-using-a-dot-runsettings-file)
  - [Настройка тестового запуска](https://github.com/Microsoft/vstest-docs/blob/master/docs/configure.md)

- **`-t|--list-tests`**

  Отображение списка всех обнаруженных тестов в текущем проекте.

- **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`. Значение по умолчанию — `minimal`. Для получения дополнительной информации см. <xref:Microsoft.Build.Framework.LoggerVerbosity>.

- Аргументы **`RunSettings`**

 Встроенные `RunSettings` передаются как последние аргументы в командной строке после "-- " (обратите внимание на пробел после "--"). Встроенные `RunSettings` указываются как пары `[name]=[value]`. Несколько пар `[name]=[value]` разделяются пробелами.

  Пример: `dotnet test -- MSTest.DeploymentEnabled=false MSTest.MapInconclusiveToFailed=True`

  Дополнительные сведения см. в статье о [передаче аргументов RunSettings с помощью командной строки](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md).

## <a name="examples"></a>Примеры

- Выполнение тестов в проекте в текущем каталоге:

  ```dotnetcli
  dotnet test
  ```

- Выполнение тестов в проекте `test1`:

  ```dotnetcli
  dotnet test ~/projects/test1/test1.csproj
  ```

- Выполнение тестов в проекте в текущем каталоге и создание файла результатов теста в формате TRX:

  ```dotnetcli
  dotnet test --logger trx
  ```

- Выполнение тестов в проекте в текущем каталоге и вывод журнала с подробными сведениями в консоль:

  ```dotnetcli
  dotnet test --logger "console;verbosity=detailed"
  ```
  
  - Выполнение тестов в проекте в текущем каталоге и тестов отчетов, которые выполнялись при сбое узла тестирования:

  ```dotnetcli
  dotnet test --blame
  ```

## <a name="filter-option-details"></a>Сведения о параметре "Фильтр"

`--filter <EXPRESSION>`

Параметр `<Expression>` имеет следующий формат: `<property><operator><value>[|&<Expression>]`.

`<property>` — это атрибут `Test Case`. Ниже приведены свойства, поддерживаемые популярными платформами модульных тестов.

| Тестовая платформа | Поддерживаемые свойства                                                                                      |
| -------------- | --------------------------------------------------------------------------------------------------------- |
| MSTest         | <ul><li>FullyQualifiedName</li><li>name</li><li>ClassName</li><li>Priority</li><li>TestCategory</li></ul> |
| xUnit          | <ul><li>FullyQualifiedName</li><li>DisplayName</li><li>Признаки</li></ul>                                   |

`<operator>` описывает связь между свойством и значением:

| Оператор | Функция        |
| :------: | --------------- |
| `=`      | Точное соответствие     |
| `!=`     | Неточное соответствие |
| `~`      | Содержит        |
| `!~`     | Не содержит    |

`<value>` — это строка. Поиск выполняется без учета регистра.

Выражение без `<operator>` автоматически считается функцией `contains` для свойства `FullyQualifiedName` (например, `dotnet test --filter xyz` совпадает с `dotnet test --filter FullyQualifiedName~xyz`).

Выражения можно объединять с условными операторами.

| Оператор            | Функция |
| ------------------- | -------- |
| <code>&#124;</code> | OR       |
| `&`                 | AND      |

При использовании условных операторов выражения можно заключать в скобки (например, `(Name~TestMethod1) | (Name~TestMethod2)`).

Дополнительные сведения и примеры использования фильтрации при выборочном модульном тестировании см. в статье [Выполнение выборочных модульных тестов](../testing/selective-unit-tests.md).

## <a name="see-also"></a>См. также

- [Платформы и целевые объекты](../../standard/frameworks.md)
- [Каталог идентификаторов сред выполнения (RID) в .NET Core](../rid-catalog.md)
- [Передача аргументов runsettings через командную строку](https://github.com/Microsoft/vstest-docs/blob/master/docs/RunSettingsArguments.md)
