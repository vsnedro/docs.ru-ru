---
title: Команда dotnet nuget update source
description: Команда dotnet nuget update source обновляет существующий источник в файлах конфигурации NuGet.
ms.date: 03/20/2020
ms.openlocfilehash: a8658c78c095ad4b9272d97200e1d6466cbe658b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537858"
---
# <a name="dotnet-nuget-update-source"></a>dotnet nuget update source

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.200 и более поздних версий

## <a name="name"></a>name

`dotnet nuget update source` — обновление источника NuGet.

## <a name="synopsis"></a>Краткий обзор

```dotnetcli
dotnet nuget update source <NAME> [--source <SOURCE>] [--username <USER>]
    [--password <PASSWORD>] [--store-password-in-clear-text]
    [--valid-authentication-types <TYPES>] [--configfile <FILE>]

dotnet nuget update source -h|--help
```

## <a name="description"></a>Описание

Команда `dotnet nuget update source` обновляет существующий источник в файлах конфигурации NuGet.

## <a name="arguments"></a>Аргументы

- **`NAME`**

  Имя источника.

## <a name="options"></a>Параметры

- **`--configfile <FILE>`**

  Файл конфигурации NuGet. Если этот параметр указан, будут использоваться только параметры из этого файла. Если не указано, будет использоваться иерархия файлов конфигурации из текущего каталога. Дополнительные сведения см. в статье [Распространенные конфигурации NuGet](/nuget/consume-packages/configuring-nuget-behavior).

- **`-p|--password <PASSWORD>`**

  Пароль, используемый при подключении к источнику, прошедшему проверку подлинности.

- **`-s|--source <SOURCE>`**

  Путь к источнику пакета.

- **`--store-password-in-clear-text`**

  Включает сохранение учетных данных переносимого источника пакетов путем отключения шифрования паролей.

- **`-u|--username <USER>`**

  Имя пользователя, используемое при подключении к источнику, прошедшему проверку подлинности.

- **`--valid-authentication-types <TYPES>`**

  Разделенный запятыми список допустимых типов проверки подлинности для этого источника. Задайте значение `basic`, если сервер объявляет NTLM или Negotiate. Ваши учетные данные следует отправлять с помощью базового механизма, например, при использовании PAT с локальным Azure DevOps Server. К другим допустимым значениям относятся `negotiate`, `kerberos`, `ntlm` и `digest`, но они вряд ли будут полезны.

## <a name="examples"></a>Примеры

- Обновите источник с именем `mySource`:

  ```dotnetcli
  dotnet nuget update source mySource --source c:\packages
  ```

## <a name="see-also"></a>См. также

- [Разделы источников пакетов в файлах NuGet.config](/nuget/reference/nuget-config-file#package-source-sections)

- [Команда sources (nuget.exe)](/nuget/reference/cli-reference/cli-ref-sources)
