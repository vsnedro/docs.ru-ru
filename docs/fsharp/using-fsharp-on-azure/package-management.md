---
title: 'Использование Управление пакетами с F # для Azure'
description: 'Использование пакет или NuGet для управления зависимостями Azure на F #'
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 7816c82e87db113a35fef967886c8c3e27959332
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756238"
---
# <a name="package-management-for-f-azure-dependencies"></a>Управление пакетами для зависимостей F# в Azure

Получение пакетов для разработки Azure несложно при использовании диспетчера пакетов. Два варианта — [пакет](https://fsprojects.github.io/Paket/) и [NuGet](https://www.nuget.org/).

## <a name="using-paket"></a>Использование пакет

Если вы используете [пакет](https://fsprojects.github.io/Paket/) в качестве диспетчера зависимостей, вы можете использовать это `paket.exe` средство для добавления зависимостей Azure. Пример:

```console
> paket add nuget WindowsAzure.Storage
```

Или, если вы используете [Mono](https://www.mono-project.com/) для кросс-платформенной разработки .NET:

```console
> mono paket.exe add nuget WindowsAzure.Storage
```

При этом будет добавлен `WindowsAzure.Storage` набор зависимостей пакета для проекта в текущем каталоге, изменен `paket.dependencies` файл и загружен пакет. Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:

```console
> paket install
```

Или, для разработки Mono:

```console
> mono paket.exe install
```

Вы можете обновить все зависимости пакета до последней версии следующим образом:

```console
> paket update
```

Или, для разработки Mono:

```console
> mono paket.exe update
```

## <a name="using-nuget"></a>Использование NuGet

Если вы используете [NuGet](https://www.nuget.org/) в качестве диспетчера зависимостей, это средство можно использовать `nuget.exe` для добавления зависимостей Azure. Пример:

```console
> nuget install WindowsAzure.Storage -ExcludeVersion
```

Или, для разработки Mono:

```console
> mono nuget.exe install WindowsAzure.Storage -ExcludeVersion
```

Это приведет к добавлению `WindowsAzure.Storage` набора зависимостей пакета для проекта в текущем каталоге и загрузке пакета. Если вы ранее настроили зависимости или работаете с проектом, в котором зависимости были настроены другим разработчиком, вы можете разрешить и установить зависимости в локальной среде следующим образом:

```console
> nuget restore
```

Или, для разработки Mono:

```console
> mono nuget.exe restore
```

Вы можете обновить все зависимости пакета до последней версии следующим образом:

```console
> nuget update
```

Или, для разработки Mono:

```console
> mono nuget.exe update
```

## <a name="referencing-assemblies"></a>Ссылки на сборки

Чтобы использовать пакеты в скрипте F #, необходимо сослаться на сборки, содержащиеся в пакетах, с помощью `#r` директивы. Пример:

```fsharp
> #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"
```

Как видите, необходимо указать относительный путь к библиотеке DLL и полное имя библиотеки DLL, которое может не совпадать с именем пакета. Путь будет содержать версию платформы и, возможно, номер версии пакета. Чтобы найти все установленные сборки, можно использовать в командной строке Windows нечто подобное:

```console
> cd packages/WindowsAzure.Storage
> dir /s/b *.dll
```

Или в оболочке UNIX примерно так:

```console
> find packages/WindowsAzure.Storage -name "*.dll"
```

При этом будут предоставлены пути к установленным сборкам. После этого можно выбрать правильный путь к версии платформы.
