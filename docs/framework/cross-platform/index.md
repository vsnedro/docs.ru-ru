---
title: Разработка на .NET Framework для разных платформ
ms.date: 10/21/2020
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
ms.openlocfilehash: ef8fae4238f404d650528d25ab873fa48e2c0703
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687745"
---
# <a name="develop-for-multiple-platforms-with-net-framework"></a>Разработка на .NET Framework для разных платформ

.NET Framework и Visual Studio позволяют вам разрабатывать приложения для платформ как от Майкрософт, так и от других поставщиков.

[!INCLUDE [net-framework-future](../../../includes/net-framework-future.md)]

## <a name="options-for-cross-platform-development"></a>Варианты для межплатформенной разработки

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Для разработки приложений для нескольких платформ можно использовать один исходный код или двоичные файлы, а также осуществлять вызовы между кодом .NET Framework и API-интерфейсами среды выполнения Windows.

|Цель...|Используйте...|
|-----------------------|------------|
|Совместное использование кода между приложениями Windows Phone 8.1 и Windows 8.1|**Общие проекты** (шаблон универсальных приложений в Visual Studio 2013 с обновлением 2).<br /><br /> -   Поддержка Visual Basic сейчас отсутствует.<br />-   Вы можете отделять код для конкретных платформ с помощью операторов #`if`.<br /><br /> Дополнительные сведения см. в разделе:<br /><br /> -   [Начало разработки](/windows/uwp/get-started/create-uwp-apps)<br />-   [Using Visual Studio to build Universal XAML Apps](https://devblogs.microsoft.com/visualstudio/using-visual-studio-to-build-universal-xaml-apps/) (запись блога "Использование Visual Studio для создания универсальных XAML-приложений")<br />-   [Using Visual Studio to Build XAML Converged Apps](https://channel9.msdn.com/Events/Build/2014/3-591) (видео "Использование Visual Studio для создания конвергентных XAML-приложений")|
|Совместное использование двоичных файлов приложениями для различных платформ|**Проекты переносимой библиотеки классов** для кода, не зависящего от платформы.<br /><br /> -   Такой подход обычно используется для кода, реализующего бизнес-логику.<br />-   Можно использовать Visual Basic или C#.<br />-   Поддержка API-интерфейсов зависит от платформы.<br />-   Проекты переносимой библиотеки классов для Windows 8.1 и Windows Phone 8.1 поддерживают API-интерфейсы среды выполнения Windows и XAML. Эти функции недоступны в более старых версиях переносимой библиотеки классов.<br />-   При необходимости можно абстрагировать код для определенной платформы, используя интерфейсы или абстрактные классы.<br /><br /> Дополнительные сведения см. в разделе:<br /><br /> -   [Переносимая библиотека классов](portable-class-library.md)<br />-   [How to Make Portable Class Libraries Work for You](/archive/blogs/dsplaisted/how-to-make-portable-class-libraries-work-for-you) (запись блога "Эффективное использование переносимых библиотек классов")<br />-   [Использование переносимой библиотеки классов с шаблоном MVVM](using-portable-class-library-with-model-view-view-model.md) <br />-   [Ресурсы приложений для библиотек под несколько платформ](app-resources-for-libraries-that-target-multiple-platforms.md) <br />-   [.NET Portability Analyzer](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) (расширение Visual Studio)|
|Совместное использование кода между приложениями для платформ, отличных от Windows Phone 8.1 и Windows 8.1|Функция **Добавить как ссылку** .<br /><br /> -   Этот подход применим к логике, которая действует в двух разных приложениях, но по какой-то причине не является переносимой. Эту возможность можно использовать в коде Visual Basic или C#.<br />     Например, Windows Phone 8 и Windows 8 используют одни API среды выполнения Windows, но переносимые библиотеки классов не поддерживают среду выполнения Windows для этих платформ. Вы можете использовать `Add as link` для совместного использования кода среды выполнения Windows между приложением Windows Phone 8 и приложением Магазина Windows, предназначенного для Windows 8.<br /><br /> Дополнительные сведения см. в разделе:<br /><br /> -   [Совместное использование кода с помощью функции "Добавить как ссылку"](/previous-versions/windows/apps/jj714082(v=vs.105))<br />-   [Практическое руководство. Добавление в проект существующих элементов](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))|
|Создание приложений Магазина Windows с использованием .NET Framework или вызов API среды выполнения Windows из кода .NET Framework|**API-интерфейсы среды выполнения Windows** из кода .NET Framework на C# или Visual Basic, а также применение .NET Framework для создания приложений Microsoft Store. Следует помнить о различиях API двух платформ. Однако существуют классы, помогающие обойти эти отличия.<br /><br /> Дополнительные сведения см. в разделе:<br /><br /> -   [Поддержка приложений Microsoft Store и среды выполнения Windows в .NET Framework](support-for-windows-store-apps-and-windows-runtime.md) <br />-   [Передача URI в среду выполнения Windows](passing-a-uri-to-the-windows-runtime.md) <br />-   <xref:System.IO.WindowsRuntimeStreamExtensions><br />-    <xref:System.WindowsRuntimeSystemExtensions>|
|Создание приложений .NET Framework для платформ других поставщиков|**Ссылочные сборки переносимой библиотеки классов** в .NET Framework и расширение Visual Studio или стороннее средство, например Xamarin.<br /><br /> Дополнительные сведения см. в разделе:<br /><br /> -   [Portable Class Library now available on all platforms](https://devblogs.microsoft.com/dotnet/portable-class-library-pcl-now-available-on-all-platforms/) — переносимая библиотека классов теперь доступна на всех платформах (публикация блога)<br />-   [Документация по Xamarin](/xamarin)|
|Использование JavaScript и HTML для межплатформенной разработки|**Шаблоны универсальных приложений** в Visual Studio 2013 с обновлением 2 для разработки с помощью API-интерфейсов среды выполнения Windows под платформы Windows 8.1 и Windows Phone 8.1. Использовать JavaScript и HTML с API-интерфейсами .NET Framework для разработки кроссплатформенных приложений сейчас невозможно.<br /><br /> Дополнительные сведения см. в разделе:<br /><br /> -   [Шаблоны проектов JavaScript](/previous-versions/windows/apps/hh758331(v=win.10))<br />-   [Перенос приложения среды выполнения Windows, использующего JavaScript, на Windows Phone](/previous-versions/windows/apps/dn636144(v=win.10))|