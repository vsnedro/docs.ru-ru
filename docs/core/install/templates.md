---
title: Установка шаблонов SDK и управление ими — .NET Core
description: Сведения об установке шаблонов .NET Core в Windows, Linux и macOS.
author: adegeo
ms.author: adegeo
ms.date: 04/24/2020
zone_pivot_groups: operating-systems-set-one
no-loc:
- dotnet new
- dotnet nuget add source
ms.openlocfilehash: 09acae1409eb0492be10bd3a61b14da5be57c6c7
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324498"
---
# <a name="manage-net-project-and-item-templates"></a>Создание шаблонов проектов и элементов .NET

.NET Core предоставляет систему шаблонов, которая позволяет пользователям устанавливать или удалять шаблоны из NuGet, файла пакета NuGet или каталога файловой системы. В этой статье описывается, как управлять шаблонами .NET Core с помощью интерфейса командной строки пакета SDK для .NET Core.

Дополнительные сведения о создании шаблонов см. в [руководстве по созданию шаблонов](../tutorials/cli-templates-create-item-template.md).

## <a name="install-template"></a>Установка шаблонов

Шаблоны устанавливаются с помощью команды SDK [dotnet new](../tools/dotnet-new.md) с параметром `-i`. Можно указать идентификатор пакета NuGet шаблона или папку, содержащую файлы шаблонов.

### <a name="nuget-hosted-package"></a>Размещенный пакет NuGet

Шаблоны .NET CLI передаются в [NuGet](https://www.nuget.org/) для широкого распространения. Шаблоны также можно установить из частного веб-канала. Вместо отправки шаблона в веб-канал NuGet файлы шаблонов *nupkg* можно распространять и устанавливать вручную, как описано в разделе [Локальный пакет NuGet](#local-nuget-package).

Для получения дополнительных сведений о настройке веб-каналов NuGet см. [dotnet nuget add source](../tools/dotnet-nuget-add-source.md).

Чтобы установить пакет шаблона из веб-канала NuGet по умолчанию, используйте команду `dotnet new -i {package-id}`:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates
```

Чтобы установить пакет шаблона из веб-канала NuGet по умолчанию с конкретной версией, используйте команду `dotnet new -i {package-id}::{version}`:

```dotnetcli
dotnet new -i Microsoft.DotNet.Web.Spa.ProjectTemplates::2.2.6
```

### <a name="local-nuget-package"></a>Локальный пакет NuGet

При создании пакета шаблона создается файл *nupkg*. Если у вас есть файл *nupkg*, содержащий шаблоны, его можно установить с помощью команды `dotnet new -i {path-to-package}`:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\Some.Templates.1.0.0.nupkg
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/Some.Templates.1.0.0.nupkg
```

::: zone-end

### <a name="folder"></a>Папка

В качестве альтернативы установке шаблона из файла *nupkg* можно также установить шаблоны из папки напрямую с помощью команды `dotnet new -i {folder-path}`. Указанная папка считается идентификатором пакета шаблона для любого найденного шаблона. Любой шаблон, найденный в иерархии указанной папки, устанавливается.

::: zone pivot="os-windows"

```dotnetcli
dotnet new -i c:\code\nuget-packages\some-folder\
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -i ~/code/nuget-packages/some-folder/
```

::: zone-end

`{folder-path}`, указанный в команде, становится идентификатором пакета шаблона для всех найденных шаблонов. Как указано в разделе [Список шаблонов](#list-templates), можно получить список установленных шаблонов с помощью команды `dotnet new -u`. В этом примере идентификатор пакета шаблона отображается как папка, используемая для установки:

::: zone pivot="os-windows"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  /home/username/code/templates
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="uninstall-template"></a>Удаление шаблона

Шаблоны удаляются с помощью команды SDK [dotnet new](../tools/dotnet-new.md) с параметром `-u`. Можно указать идентификатор пакета NuGet шаблона или папку, содержащую файлы шаблонов.

### <a name="nuget-package"></a>Пакет NuGet

После установки пакета шаблона NuGet из веб-канала NuGet или файла *nupkg* можно удалить его, сославшись на идентификатор пакета NuGet.

Чтобы удалить пакет шаблона, используйте команду `dotnet new -u {package-id}`:

```dotnetcli
dotnet new -u Microsoft.DotNet.Web.Spa.ProjectTemplates
```

### <a name="folder"></a>Папка

При установке шаблонов с помощью [пути к папке](#folder) путь к папке становится идентификатором пакета шаблона.

Чтобы удалить пакет шаблона, используйте команду `dotnet new -u {package-folder-path}`:

::: zone pivot="os-windows"

```dotnetcli
dotnet new -u c:\code\nuget-packages\some-folder
```

::: zone-end

::: zone pivot="os-linux,os-macos"

```dotnetcli
dotnet new -u /home/username/code/templates
```

::: zone-end

## <a name="list-templates"></a>Список шаблонов

Используя стандартную команду удаления без идентификатора пакета, можно просмотреть список установленных шаблонов вместе с командой, которая удаляет каждый шаблон.

```console
dotnet new -u
Template Instantiation Commands for .NET Core CLI

Currently installed items:

... cut to save space ...

  c:\code\nuget-packages\some-folder
    Templates:
      A Template Console Class (templateconsole) C#
      Project for some technology (contosoproject) C#
    Uninstall Command:
      dotnet new -u c:\code\nuget-packages\some-folder
```

## <a name="install-templates-from-other-sdks"></a>Установка шаблонов из других пакетов SDK

Если вы установили каждую версию пакета SDK последовательно, например пакет SDK 2.0, пакет SDK 2.1 и т. д., у вас будут установлены все шаблоны пакета SDK. Однако если начать с более поздней версии пакета SDK, например 3.1, будут включены только шаблоны для [выпусков LTS (долгосрочная поддержка)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), и на момент выпуска пакета SDK 3.1 это пакет SDK 2.1 и пакет SDK 3.1. Шаблоны для любого другого выпуска не включаются.

Шаблоны .NET Core доступны в NuGet, и их можно установить как любые другие шаблоны. Дополнительные сведения см. в разделе [Установка размещенного пакета NuGet](#nuget-hosted-package).

| SDK              | Идентификатор пакета NuGet                                                                                                      |
|------------------|-------------------------------------------------------------------------------------------------------------------------------|
| .NET Core 2.1    | [`Microsoft.DotNet.Common.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.1) |
| .NET Core 2.2    | [`Microsoft.DotNet.Common.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.2.2) |
| .NET Core 3.0    | [`Microsoft.DotNet.Common.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.0) |
| .NET Core 3.1    | [`Microsoft.DotNet.Common.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Common.ProjectTemplates.3.1) |
| ASP.NET Core 2.1 | [`Microsoft.DotNet.Web.ProjectTemplates.2.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.1)       |
| ASP.NET Core 2.2 | [`Microsoft.DotNet.Web.ProjectTemplates.2.2`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.2.2)       |
| ASP.NET Core 3.0 | [`Microsoft.DotNet.Web.ProjectTemplates.3.0`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.0)       |
| ASP.NET Core 3.1 | [`Microsoft.DotNet.Web.ProjectTemplates.3.1`](https://www.nuget.org/packages/Microsoft.DotNet.Web.ProjectTemplates.3.1)       |

Например, пакет SDK для .NET Core включает шаблоны для консольного приложения, предназначенного для .NET Core 2.1 и .NET Core 3.1. Если ваша целевая версия — .NET Core 3.0, необходимо установить шаблоны 3.0.

01. Попробуйте создать приложение, предназначенное для .NET Core 3.0.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Если отображается сообщение об ошибке, необходимо установить шаблоны.

    > Не удалось найти установленный шаблон, соответствующий входным данным, поиск нужного шаблона в Интернете...

01. Установите шаблоны проекта .NET Core 3.0.

    ```dotnetcli
    dotnet new -i Microsoft.DotNet.Common.ProjectTemplates.3.0
    ```

01. Попробуйте создать приложение еще раз.

    ```dotnetcli
    dotnet new console --framework netcoreapp3.0
    ```

    Вы увидите сообщение о том, что проект был создан.

    > Шаблон "Консольное приложение" успешно создан.
    >
    > Обработка действий после создания... Выполнение dotnet restore для path-to-project-file.csproj... Определение проектов для восстановления... Восстановление завершено за 1,05 с для path-to-project-file.csproj.
    >
    > Восстановление выполнено.

## <a name="see-also"></a>См. также

- [Учебник. Создание шаблона элемента](../tutorials/cli-templates-create-item-template.md)
- [dotnet new](../tools/dotnet-new.md)
- [dotnet nuget add source](../tools/dotnet-nuget-add-source.md)
