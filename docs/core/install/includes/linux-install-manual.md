---
ms.openlocfilehash: 3932cf51b5194dba7956cd62ced3985a2e6311f0
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506825"
---

<!-- Note, this content is copied in ../macos.md. Any fixes should be applied there too, though content may be different -->

В качестве альтернативы диспетчерам пакетов можно скачать и вручную установить пакет SDK и среду выполнения. Ручная установка как правило выполняется в рамках тестирования непрерывной интеграции или в неподдерживаемом дистрибутиве Linux. В большинстве случаев разработчикам и пользователям рекомендуется использовать диспетчер пакетов.

При установке пакета SDK для .NET не нужно устанавливать соответствующую среду выполнения. Сначала скачайте **двоичный** выпуск пакета SDK или среды выполнения с одного из следующих сайтов:

- ✔️ [Скачиваемые файлы для .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Скачиваемые файлы .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [Скачиваемые файлы .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Все скачиваемые файлы для .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

Извлеките скачанный файл и используйте команду `export`, чтобы задать переменные, используемые .NET, а затем проверьте включение .NET в переменную PATH.

Чтобы извлечь среду выполнения и сделать команды .NET CLI доступными в терминале, сначала скачайте двоичный выпуск .NET. Затем откройте терминал и выполните следующие команды в каталоге с сохраненным файлом. Имя файла архива может отличаться в зависимости от скачанных файлов.

**Извлеките среду выполнения, используя следующую команду**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Извлеките пакет SDK, используя следующую команду**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Приведенные выше команды `export` сделают команды .NET CLI доступными только для сеанса терминала, в котором производился запуск.
>
> Вы можете изменить профиль оболочки, чтобы добавить команды окончательно. Существует несколько различных оболочек, доступных для Linux, и каждая из них имеет свой профиль. Пример:
>
> - **Оболочка Bash**: *~/.bash_profile*, *~/.bashrc*
> - **Оболочка Korn**: *~/.kshrc* или *.profile*
> - **Оболочка Z**: *~/.zshrc* или *.zprofile*
>
> Измените соответствующий исходный файл оболочки и добавьте `:$HOME/dotnet` в конец существующего оператора `PATH`. Если оператор `PATH` не указан, добавьте новую строку с `export PATH=$PATH:$HOME/dotnet`.
>
> Кроме того, добавьте `export DOTNET_ROOT=$HOME/dotnet` в конец файла.

Такой подход позволяет устанавливать разные версии в отдельные расположения и выбирать, какие из них следует использовать для каждого приложения.
