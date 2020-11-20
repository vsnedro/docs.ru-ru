---
title: Команда dotnet store
description: Команда dotnet store сохраняет указанные сборки в хранилище пакетов среды выполнения.
ms.date: 02/14/2020
ms.openlocfilehash: 8efb11c6bf648bc7787d5627e02b180abb8a0afd
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634341"
---
# <a name="dotnet-store"></a>dotnet store

**Эта статья относится к следующему:** ✔️ пакет SDK для .NET Core 2.x и более поздних версий

## <a name="name"></a>Имя

`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md).

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet store -m|--manifest <PATH_TO_MANIFEST_FILE>
    -f|--framework <FRAMEWORK_VERSION> -r|--runtime <RUNTIME_IDENTIFIER>
    [--framework-version <FRAMEWORK_VERSION>] [--output <OUTPUT_DIRECTORY>]
    [--skip-optimization] [--skip-symbols] [-v|--verbosity <LEVEL>]
    [--working-dir <WORKING_DIRECTORY>]

dotnet store -h|--help
```

## <a name="description"></a>Описание:

`dotnet store` — сохраняет указанные сборки в [хранилище пакетов среды выполнения](../deploying/runtime-store.md). По умолчанию сборки оптимизируются для целевой среды выполнения и платформы. Дополнительные сведения см. в разделе, посвященном [хранилищу пакетов среды выполнения](../deploying/runtime-store.md).

## <a name="required-options"></a>Обязательные параметры

- **`-f|--framework <FRAMEWORK>`**

  Задает [целевую платформу](../../standard/frameworks.md). Целевая платформа должна быть указана в файле проекта.

- **`-m|--manifest <PATH_TO_MANIFEST_FILE>`**

  *Файл манифеста хранилища пакетов* — это XML-файл, содержащий список сохраняемых пакетов. Формат файла манифеста совместим с форматом проекта в стиле SDK. Поэтому файл проекта, ссылающийся на требуемые пакеты, можно использовать с параметром `-m|--manifest` для сохранения сборок в хранилище пакетов среды выполнения. Чтобы указать несколько файлов манифеста, добавьте параметр и путь для каждого из них. Пример: `--manifest packages1.csproj --manifest packages2.csproj`.

- **`-r|--runtime <RUNTIME_IDENTIFIER>`**

  [Идентификатор целевой среды выполнения](../rid-catalog.md).

## <a name="optional-options"></a>Необязательные параметры

- **`--framework-version <FRAMEWORK_VERSION>`**

  Указывает версию пакета SDK для .NET. Этот параметр позволяет выбрать определенную версию платформы, отличную от версии, заданной с помощью параметра `-f|--framework`.

- **`-h|--help`**

  Выводит справочные сведения.

- **`-o|--output <OUTPUT_DIRECTORY>`**

  Определяет путь к хранилищу пакетов среды выполнения. Если значение не указано, по умолчанию используется подкаталог *store* каталога установки .NET в профиле пользователя.

- **`--skip-optimization`**

  Пропуск этапа оптимизации.

- **`--skip-symbols`**

  Пропуск создания символов. В настоящее время символы можно создавать только в Windows и Linux.

- **`-v|--verbosity <LEVEL>`**

  Задает уровень детализации команды. Допустимые значения: `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` и `diag[nostic]`.

- **`-w|--working-dir <WORKING_DIRECTORY>`**

  Рабочий каталог, используемый командой. Если значение не указано, используется подкаталог *obj* в текущем каталоге.

## <a name="examples"></a>Примеры

- Сохранение пакетов, указанных в файле проекта *packages.csproj* для .NET Core 2.0.0:

  ```dotnetcli
  dotnet store --manifest packages.csproj --framework-version 2.0.0
  ```

- Сохранение пакетов, указанных в файле *packages.csproj*, без оптимизации:

  ```dotnetcli
  dotnet store --manifest packages.csproj --skip-optimization
  ```

## <a name="see-also"></a>См. также раздел

- [Хранилище пакетов среды выполнения](../deploying/runtime-store.md)
