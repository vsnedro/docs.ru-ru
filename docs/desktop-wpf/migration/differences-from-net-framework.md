---
title: Различия между .NET Core и .NET Framework
description: Описание различий между реализацией Windows Presentation Foundation (WPF) в .NET Framework и .NET Core. При переносе приложения следует учитывать эти несовместимости.
author: adegeo
ms.date: 09/21/2019
ms.author: adegeo
ms.openlocfilehash: 3bedc30046c36d4c5430feedf5854276ebaef8aa
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325693"
---
# <a name="differences-in-wpf"></a>Отличия в WPF

В этой статье описываются различия между Windows Presentation Foundation (WPF) в .NET Core и .NET Framework. WPF для .NET Core — [платформа с открытым исходным кодом](https://github.com/dotnet/wpf), ответвленная от первоначального исходного кода WPF для .NET Framework.

.NET Core не поддерживает несколько функций .NET Framework. Дополнительные сведения о неподдерживаемых технологиях см. в статье [Технологии .NET Framework, недоступные в .NET Core](../../core/porting/net-framework-tech-unavailable.md).

[!INCLUDE [desktop guide under construction](../../../includes/desktop-guide-preview-note.md)]

## <a name="sdk-style-projects"></a>Проекты в стиле SDK

.NET Core использует файлы проектов в стиле пакетов SDK. Эти файлы проектов отличаются от традиционных файлов проектов .NET Framework, управляемых Visual Studio. Для переноса приложений WPF .NET Framework в .NET Core необходимо преобразовать их проекты. Дополнительные сведения см. в разделе [Руководство по миграции приложений WPF в .NET Core 3.0](convert-project-from-net-framework.md).

## <a name="nuget-package-references"></a>Ссылки на пакет NuGet

Если приложение .NET Framework перечисляет зависимости NuGet в файле *packages.config*, выполните миграцию в формат [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files):

1. В Visual Studio откройте окно **Обозревателя решений**.
1. В проекте WPF щелкните правой кнопкой мыши **packages.config** > **Перенести packages.config в PackageReference**.

![Обновление до PackageReference](media/differences-from-net-framework/package-reference-migration.png)

Откроется диалоговое окно с вычисленными зависимостями NuGet верхнего уровня и вопросом, какие другие пакеты NuGet следует повысить до верхнего уровня. Выберите **ОК**, и файл *packages.config* будет удален из проекта, а элементы `<PackageReference>` будут добавлены в файл проекта.

Если в проекте используется `<PackageReference>`, пакеты не хранятся локально в папке *Пакеты*, они хранятся глобально. Откройте файл проекта и удалите все элементы `<Analyzer>`, которые ссылаются на папку *Пакеты*. Эти анализаторы автоматически добавляются к ссылкам на пакет NuGet.

## <a name="code-access-security"></a>Управление доступом для кода

Управление доступом для кода (CAS) не поддерживается .NET Core или WPF для .NET Core. Все функции, связанные с CAS, работают исходя из предположения полного доверия. WPF для .NET Core удаляет код, связанный с CAS. Поверхность открытого API этих типов по-прежнему существует, чтобы обеспечить успешный вызов этих типов.

Открыто определенные типы, связанные с CAS, были перемещены из сборок WPF в сборки библиотеки Core .NET. В этих сборках WPF установлена пересылка типов к новому расположению перемещенных типов.

| Исходная сборка | Целевая сборка | Type                |
| --------------- | --------------- | ------------------- |
| *WindowsBase.dll* | *System.Security.Permissions.dll* | <xref:System.Security.Permissions.MediaPermission> <br /> <xref:System.Security.Permissions.MediaPermissionAttribute> <br /> <xref:System.Security.Permissions.MediaPermissionAudio> <br /> <xref:System.Security.Permissions.MediaPermissionImage> <br /> <xref:System.Security.Permissions.MediaPermissionVideo> <br /> <xref:System.Security.Permissions.WebBrowserPermission> <br /> <xref:System.Security.Permissions.WebBrowserPermissionAttribute> <br /> <xref:System.Security.Permissions.WebBrowserPermissionLevel> |
| *System.Xaml.dll* | *System.Security.Permissions.dll* | <xref:System.Xaml.Permissions.XamlLoadPermission> |
| *System.Xaml.dll* | *System.Windows.Extension.dll*    | <xref:System.Xaml.Permissions.XamlAccessLevel><br/> |

> [!NOTE]
> Чтобы свести к минимуму трения при переносе, функции хранения и извлечения информации, связанной со следующими свойствами, были оставлены в типе `XamlAccessLevel`.
>
> - `PrivateAccessToTypeName`
> - `AssemblyNameString`

## <a name="next-steps"></a>Следующие шаги

- [Узнайте, как перенести приложение WPF .NET Framework в .NET Core.](convert-project-from-net-framework.md)
