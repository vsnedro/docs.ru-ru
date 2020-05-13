---
title: Команда dotnet vstest
description: Команда dotnet vstest выполняет сборку проекта и всех его зависимостей.
ms.date: 02/27/2020
ms.openlocfilehash: f7db58f4aab59354b8c69ce0371324c23482dafe
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975398"
---
# <a name="dotnet-vstest"></a>dotnet vstest

**Эта статья относится к следующему.** ✔️ SDK для .NET Core 2.1 и более поздних версий

> [!IMPORTANT]
> Команда `dotnet vstest` заменяется на `dotnet test`, которую теперь можно использовать для запуска сборок. См. раздел [`dotnet test`](dotnet-test.md).

## <a name="name"></a>name

`dotnet-vstest` — запускает тесты из указанных сборок.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet vstest [<TEST_FILE_NAMES>] [--Blame] [--Diag <PATH_TO_LOG_FILE>]
    [--Framework <FRAMEWORK>] [--InIsolation] [-lt|--ListTests <FILE_NAME>]
    [--logger <LOGGER_URI/FRIENDLY_NAME>] [--Parallel]
    [--ParentProcessId <PROCESS_ID>] [--Platform] <PLATFORM_TYPE>
    [--Port <PORT>] [--ResultsDirectory<PATH>] [--Settings <SETTINGS_FILE>]
    [--TestAdapterPath <PATH>] [--TestCaseFilter <EXPRESSION>]
    [--Tests <TEST_NAMES>] [[--] <args>...]]

dotnet vstest -?|--Help
```

## <a name="description"></a>Описание

Команда `dotnet-vstest` запускает приложение командной строки `VSTest.Console` для выполнения автоматического модульного тестирования.

## <a name="arguments"></a>Аргументы

- **`TEST_FILE_NAMES`**

  Запустите тесты из указанных сборок. Для разделения имен тестовых сборок используйте пробелы. Поддерживаются подстановочные знаки.

## <a name="options"></a>Параметры

- **`--Blame`**

  Выполнение тестов в режиме обвинения. Этот параметр полезен при изоляции проблемных тестов, которые приводят к аварийному завершению хоста для тестов. Он создает в текущем каталоге выходной файл *Sequence.xml*, который записывает порядок выполнения тестов перед сбоем.

- **`--Diag <PATH_TO_LOG_FILE>`**

  Включает ведение подробных журналов для платформы тестирования. Журналы записываются в указанный файл.

- **`--Framework <FRAMEWORK>`**

  Целевая версия платформы .NET Framework, используемая для выполнения тестов. Примеры допустимых значений: `.NETFramework,Version=v4.6` или `.NETCoreApp,Version=v1.0`. Другие поддерживаемые значения: `Framework40`, `Framework45`, `FrameworkCore10` и `FrameworkUap10`.

- **`--InIsolation`**

  Запуск тестов в изолированном процессе. Это снижает вероятность остановки процесса *vstest.console.exe* при возникновении ошибки в тестах, однако тесты могут выполняться медленнее.

- **`-lt|--ListTests <FILE_NAME>`**

  Перечисление всех обнаруженных тестов из указанного контейнера тестов.

- **`--logger <LOGGER_URI/FRIENDLY_NAME>`**

  Укажите средство ведения журнала результатов тестирования.

  - Чтобы опубликовать результаты теста в Team Foundation Server, используйте поставщик средства ведения журнала `TfsPublisher`:

    ```console
    /logger:TfsPublisher;
        Collection=<team project collection url>;
        BuildName=<build name>;
        TeamProject=<team project name>
        [;Platform=<Defaults to "Any CPU">]
        [;Flavor=<Defaults to "Debug">]
        [;RunTitle=<title>]
    ```

  - Чтобы записать результаты в файл результатов теста Visual Studio (TRX), используйте поставщик средства ведения журнала `trx`. Этот параметр создает файл журнала с заданным именем в каталоге результатов теста. Если `LogFileName` не указан, для хранения результатов теста создается уникальное имя файла.

    ```console
    /logger:trx [;LogFileName=<Defaults to unique file name>]
    ```

- **`--Parallel`**

  Выполняйте тесты в параллельном режиме. По умолчанию для использования все доступные на компьютере ядра. Укажите явное число ядер, задав свойство `MaxCpuCount` в узле `RunConfiguration` в файле *runsettings*.

- **`--ParentProcessId <PROCESS_ID>`**

  Идентификатор родительского процесса, отвечающего за запуск текущего процесса.

- **`--Platform <PLATFORM_TYPE>`**

  Архитектура целевой платформы, используемая для выполнения тестов. Допустимые значения: `x86`, `x64` и `ARM`.

- **`--Port <PORT>`**

  Указывает порт для подключения сокета и получения сообщений о событиях.

- **`--ResultsDirectory:<PATH>`**

  По указанному пути будет создан каталог с результатами теста, если этот путь не существует.

- **`--Settings <SETTINGS_FILE>`**

  Параметры, используемые при выполнении тестов.

- **`--TestAdapterPath <PATH>`**

  Используйте пользовательские адаптеры теста из указанного пути (при наличии) в тестовом запуске.

- **`--TestCaseFilter <EXPRESSION>`**

  Запуск тестов, соответствующих заданному выражению. `<EXPRESSION>` имеет формат `<property>Operator<value>[|&<EXPRESSION>]`, где Operator принимает одно из следующих значений: `=`, `!=` или `~`. Оператор `~` имеет семантику "содержит" и применяется для строковых свойств, таких как `DisplayName`. Скобки `()` используются для группировки частей выражений. Дополнительные сведения см. в документе о [фильтре TestCase](https://github.com/Microsoft/vstest-docs/blob/master/docs/filter.md).

- **`--Tests <TEST_NAMES>`**

  Выполните тесты с именами, которые соответствуют предусмотренным значениям. Для разделения значений используйте запятые.

- **`-?|--Help`**

  Выводит краткую справку по команде.

- **`@<file>`**

  Считывает файл ответов с дополнительными параметрами.

- **`args`**

  Задает дополнительные аргументы, передаваемые адаптеру. Аргументы указываются как пары имя-значение в формате `<n>=<v>`, где `<n>` является именем аргумента, а `<v>` — значением аргумента. Для разделения аргументов используйте пробел.

## <a name="examples"></a>Примеры

Запуск тестов в *mytestproject.dll*:

```dotnetcli
dotnet vstest mytestproject.dll
```

Запуск тестов в *mytestproject.dll* с экспортом в настраиваемую папку с пользовательским именем:

```dotnetcli
dotnet vstest mytestproject.dll --logger:"trx;LogFileName=custom_file_name.trx" --ResultsDirectory:custom/file/path
```

Запуск тестов в *mytestproject.dll* и *myothertestproject.exe*:

```dotnetcli
dotnet vstest mytestproject.dll myothertestproject.exe
```

Запуск тестов `TestMethod1`:

```dotnetcli
dotnet vstest /Tests:TestMethod1
```

Запуск тестов `TestMethod1` и `TestMethod2`:

```dotnetcli
dotnet vstest /Tests:TestMethod1,TestMethod2
```

## <a name="see-also"></a>См. также

- [Параметры командной строки для VSTest.Console.exe](/visualstudio/test/vstest-console-options)
