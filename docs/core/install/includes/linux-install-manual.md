---
ms.openlocfilehash: e7d35045892c62f759aad5067962ac5c15a9fb8b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602702"
---

Как пакет SDK для .NET Core, так и среду выполнения .NET Core можно установить вручную после скачивания. При установке пакета SDK для .NET Core не нужно устанавливать соответствующую среду выполнения. Сначала скачайте двоичный выпуск пакета SDK или среды выполнения с одного из следующих сайтов:

- ✔️ [Предварительные версии скачиваемых файлов .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Скачиваемые файлы .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ❌ [Скачиваемые файлы .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- ❌ [Скачиваемые файлы .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- ✔️ [Скачиваемые файлы .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

Извлеките скачанный файл и используйте команду `export`, чтобы задать переменные, используемые .NET Core, а затем проверьте включение .NET Core в переменную PATH.

Чтобы извлечь среду выполнения и сделать команды .NET Core CLI доступными в терминале, сначала скачайте двоичный выпуск .NET Core. Затем откройте терминал и выполните следующие команды в каталоге с сохраненным файлом.

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Приведенные выше команды `export` сделают команды .NET Core CLI доступными только для сеанса терминала, в котором производился запуск.
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
