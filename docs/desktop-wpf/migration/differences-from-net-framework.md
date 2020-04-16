---
title: Различия между рамками .NET и ядром .NET
description: Описывает различия между реализацией .NET Framework Фонда презентаций Windows (WPF) и .NET Core WPF. При миграции приложения следует учитывать эти несовместимость.
author: thraka
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 4386654aad205e3c9f2cbd986d7b812e261e737f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "81433136"
---
# <a name="differences-in-wpf"></a>Различия в WPF

В этой статье описаны различия между Фондом презентаций Windows (WPF) на .NET Core и .NET Framework. WPF для .NET Core — это платформа с [открытым исходным кодом](https://github.com/dotnet/wpf) с открытым исходным кодом, раздвинутый с исходным кодом.NET Framework.

Есть несколько особенностей рамочного соглашения .NET, которые .NET Core не поддерживает. Для получения дополнительной информации [.NET Framework technologies unavailable on .NET Core](../../core/porting/net-framework-tech-unavailable.md)о неподдерживаемых технологиях см.

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Проекты в стиле SDK

.NET Core использует файлы проектов в стиле SDK. Эти файлы проекта отличаются от традиционных файлов проекта .NET Framework, управляемых Visual Studio. Чтобы перенести приложения .NET Framework WPF в ядро .NET, необходимо преобразовать свои проекты. Для получения дополнительной информации [см.](convert-project-from-net-framework.md)

## <a name="nuget-package-references"></a>Ссылки на пакет NuGet

Если приложение .NET Framework перечисляет свои зависимости NuGet в файле [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) *packages.config,* переноситесь в формат:

1. В Visual Studio откройте панель **Solution Explorer.**
1. В вашем проекте WPF, правой кнопкой мыши **packages.config** > **Мигрировать Migrate packages.config к PackageReference**.

![Обновление до PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Появится диалог, показывающий рассчитанные зависимые от NuGet верхнего уровня и спрашивающий, какие другие пакеты NuGet следует продвигать на высший уровень. Выберите **OK** и файл *packages.config* будет `<PackageReference>` удален из проекта, и элементы будут добавлены в файл проекта.

Когда ваш `<PackageReference>`проект использует, пакеты не хранятся локально в папке *пакетов,* они хранятся по всему миру. Откройте файл проекта `<Analyzer>` и удалите все элементы, относящееся к папке *Пакетов.* Эти анализаторы автоматически включаются со ссылками на пакет NuGet.

## <a name="code-access-security"></a>Управление доступом для кода

Code Access Security (CAS) не поддерживается .NET Core или WPF для .NET Core. Все функции, связанные с CAS, рассматриваются в соответствии с предположением о полном доверии. WPF для .NET Core удаляет код, связанный с CAS. Публичная поверхность API этих типов по-прежнему существует для обеспечения успеха вызовов в эти типы.

Публично определенные типы, связанные с CAS, были перемещены из собраний WPF и в сборки CoreFX. Сборки WPF имеют набор для переадресов к новому местоположению перемещенных типов.

| Сборка исходных источников | Целевая сборка | Тип                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> Для минимизации трения порта, функциональность для хранения и извлечения информации, `XamlAccessLevel` связанной со следующими свойствами, была сохранена в типе.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Следующие шаги

- [Узнайте, как портировать приложение .NET Framework WPF в ядро .NET.](convert-project-from-net-framework.md)
