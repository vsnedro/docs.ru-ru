---
title: Целевые платформы в проектах в стиле SDK — .NET
description: Сведения о целевых версиях платформы для приложений и библиотек .NET.
ms.date: 11/06/2020
ms.custom: updateeachrelease
ms.technology: dotnet-standard
ms.openlocfilehash: a37634bc9f4cbee5f7901fcb085d3801a7452573
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94441052"
---
# <a name="target-frameworks-in-sdk-style-projects"></a>Целевые платформы в проектах в стиле SDK

При выборе целевой платформы для приложения или библиотеки вы указываете набор API-интерфейсов, которые вы хотите сделать доступными для приложения или библиотеки. Целевая платформа указывается в файле проекта с помощью моникеров целевой платформы (TFM).

Приложение или библиотека могут быть предназначены для версии [.NET Standard](net-standard.md). Версии .NET Standard представляют стандартные наборы API-интерфейсов во всех реализациях .NET. Например, библиотека может быть предназначена для .NET Standard 1.6 и получить доступ к API-интерфейсам, которые работают в .NET Core и .NET Framework с одной и той же базой кода.

Приложение или библиотека могут также работать в конкретной реализации .NET. В этом случае они получают доступ к API-интерфейсам конкретной реализации. Например, приложение, предназначенное для Xamarin.iOS (например, `Xamarin.iOS10`), получает доступ к предоставленным Xamarin iOS программам-оболочкам API для iOS 10 или приложение, ориентированное на универсальную платформу Windows (UWP, `uap10.0`) имеет доступ к API-интерфейсам, которые компилируются для устройств под управлением Windows 10.

Для некоторых целевых платформ (например, .NET Framework) API-интерфейсы определяются сборками, устанавливаемыми платформой в системе, в число которых могут входить API-интерфейсы платформы приложений (например, ASP.NET).

Для целевых платформ на основе пакетов (например, .NET 5, .NET Core и .NET Standard) API-интерфейсы определяются пакетами в составе приложения или библиотеки. *Метапакет* — это пакет NuGet, не имеющий собственного содержимого, но имеющий список зависимостей (другие пакеты). В этом случае целевая платформа на основе пакетов NuGet неявно задает метапакет, который ссылается на все пакеты, составляющие платформу.

## <a name="latest-versions"></a>Последние версии

В приведенной ниже таблице определены наиболее распространенные целевые платформы, способы их указания и реализованные в них версии [.NET Standard](net-standard.md). Эти версии целевой платформ являются последними стабильными версиями. Предварительные версии здесь не упоминаются. Моникер целевой платформы (TFM) является стандартизированный форматом маркера для указания целевой платформы приложения или библиотеки .NET.

| Целевая платформа      | Последняя версия <br/> Стабильная версия | Моникер целевой платформы (TFM) | Реализовано <br/> Версия .NET Standard |
| :-: | :-: | :-: | :-: |
| .NET 5                | 5,0                         | net5.0                         | Недоступно                                     |
| .NET Standard         | 2.1                         | netstandard2.1                 | Недоступно                                     |
| .NET Core             | 3.1                         | netcoreapp3.1                  | 2.1                                     |
| .NET Framework        | 4.8                         | net48                          | 2.0                                     |

## <a name="supported-target-frameworks"></a>Неподдерживаемые целевые платформы

Целевая платформа обычно называется по TFM. В следующей таблице показаны целевые платформы, поддерживаемые пакетом SDK для .NET и клиентом NuGet. Эквивалентные обозначения отображаются в скобках. Например, `win81` является эквивалентом TFM для `netcore451`.

| Требуемая версия .NET Framework           | TFM |
| -------------------------- | --- |
| .NET 5 (и .NET Core)     | netcoreapp1.0<br>netcoreapp1.1<br>netcoreapp2.0<br>netcoreapp2.1<br>netcoreapp2.2<br>netcoreapp3.0<br>netcoreapp3.1<br>net5.0* |
| .NET Standard              | netstandard1.0<br>netstandard1.1<br>netstandard1.2<br>netstandard1.3<br>netstandard1.4<br>netstandard1.5<br>netstandard1.6<br>netstandard2.0<br>netstandard2.1 |
| .NET Framework             | net11<br>net20<br>net35<br>net40<br>net403<br>net45<br>net451<br>net452<br>net46<br>net461<br>net462<br>net47<br>net471<br>net472<br>net48 |
| Магазин Windows              | netcore [netcore45]<br>netcore45 [win] [win8]<br>netcore451 [win81] |
| .NET Micro Framework       | netmf |
| Silverlight                | sl4<br>sl5 |
| Windows Phone              | wp [wp7]<br>wp7<br>wp75<br>wp8<br>wp81<br>wpa81 |
| Универсальная платформа Windows | uap [uap10.0]<br>uap10.0 [win10] [netcore50] |

\* .NET 5.0 и более поздние версии TFM включают варианты для конкретной операционной системы. Дополнительные сведения см. в следующем разделе [TFM .NET 5 для конкретной ОС](#net-5-os-specific-tfms).

### <a name="net-5-os-specific-tfms"></a>TFM .NET 5 для конкретной ОС

Для каждого TFM .NET 5.0 и более поздних версий, например `net5.0`, существуют варианты TFM, включающие привязки для конкретной ОС. Доступные параметры показаны в следующей таблице.

| Формат ОС | Пример        |
|--------------------|----------------|
| \<base-tfm>-android | net5.0-android |
| \<base-tfm>-ios     | net5.0-ios     |
| \<base-tfm>-macos   | net5.0-macos   |
| \<base-tfm>-tvos    | net5.0-tvos    |
| \<base-tfm>-watchos | net5.0-watchos |
| \<base-tfm>-windows | net5.0-windows |

TFM `net5.0` содержит только кроссплатформенные технологии. Указание конкретной операционной системы TFM делает API, которые относятся к определенной операционной системе, доступными для приложения, например Windows Forms или привязки iOS. TFM для конкретной ОС также наследуют все API, доступные для TFM `net5.0`.

Чтобы сделать приложение кроссплатформенным, можно ориентироваться на несколько TFM для определенных операционных систем и добавить условия платформы для вызовов API, зависящих от операционной системы, с помощью директив препроцессора `#if`.

В следующей таблице показана совместимость TFM .NET 5 с TFM для предыдущих версий .NET.

| TFM             | Совместимость                                            | Примечания |
|-----------------|------------------------------------------------------------|-|
| net5.0          | net1.4 (с предупреждением NU1701)<br />netcoreapp1.3.1 (предупреждение при ссылке на WinForms или WPF)<br />netstandard1.2.1 | |
| net5.0-android  | xamarin.android (и все остальное, унаследованное от `net5.0`) | |
| net5.0-ios      | xamarin.ios (и все остальное, унаследованное от `net5.0`) | |
| net5.0-macos    | xamarin.mac (и все остальное, унаследованное от `net5.0`) | |
| net5.0-tvos     | xamarin.tvos (и все остальное, унаследованное от `net5.0`) | |
| net5.0-watchos  | xamarin.watchos (и все остальное, унаследованное от `net5.0`) | |
| net5.0-windows  | netcoreapp1.3.1 (и все остальное, унаследованное от `net5.0`) | Включает API WinForms, WPF и UWP.<br />Дополнительные сведения см. в разделе [Вызов API среды выполнения Windows в классических приложениях](/windows/apps/desktop/modernize/desktop-to-uwp-enhance). |

#### <a name="suggested-targets"></a>Предлагаемые целевые объекты

Используйте эти рекомендации, чтобы определить, какие TFM использовать в приложении:

- Приложения, переносимые на несколько платформ, должны быть ориентированы на `net5.0`. Сюда входит большинство библиотек, а также ASP.NET Core и Entity Framework.

- Библиотеки для конкретных платформ должны быть ориентированы на варианты приложения для определенных платформ. Например, в проектах WinForms и WPF следует ориентироваться `net5.0-windows`.

- Модели кроссплатформенных приложений (Xamarin Forms, ASP.NET Core) и соединительные пакеты (Xamarin Essentials) должны быть ориентированы как минимум на `net5.0`, но также могут быть ориентированы на дополнительные варианты приложения для определенных платформ, чтобы облегчить дополнительные API и функции.

#### <a name="os-version-in-tfms"></a>Версия ОС в TFM

Можно также указать дополнительную версию ОС в конце TFM, например `net5.0-ios13.0`, которая указывает, какие API доступны для приложения. (Пакет SDK для .NET 5 будет обновлен для включения поддержки более новых версий ОС по мере их выпуска.) Чтобы получить доступ к вновь выпущенным API, увеличьте версию ОС в TFM. Вы по-прежнему можете сделать приложение совместимым с более ранними версиями ОС (и добавить условия для вызовов API более поздних версий), добавив элемент `SupportedOSPlatformVersion` в файл проекта. Элемент `SupportedOSPlatformVersion` указывает минимальную версию ОС, необходимую для запуска приложения.

Например, следующий фрагмент файла проекта указывает, что API iOS 14 доступны для приложения, но могут работать в iOS 13 или более поздней версии.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>net5.0-ios14.0</TargetFramework>
    <SupportedOSPlatformVersion>13.0</SupportedOSPlatformVersion> (minimum os platform version)
  </PropertyGroup>

  ...

</Project>
```

## <a name="how-to-specify-a-target-framework"></a>Как указать целевую платформу

Целевые платформы указываются в файле проекта. Если указана одна целевая платформа, используйте [элемент TargetFramework](../core/project-sdk/msbuild-props.md#targetframework). В следующем файле проекта консольного приложения показано, как указать целевую платформу .NET 5.0:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>

</Project>
```

При указании нескольких целевых платформ можно условно ссылаться на сборки для каждой целевой платформы. В коде можно условно компилировать эти сборки с использованием символов препроцессора с логикой *if-then-else*.

Следующий файл проекта библиотеки предназначен для AP .NET Standard (`netstandard1.4`) и .NET Framework (`net40` и `net45`). Используйте множественный [элемент TargetFrameworks](../core/project-sdk/msbuild-props.md#targetframeworks) с несколькими целевыми платформами. Атрибуты `Condition` включают пакеты, связанные с конкретной реализацией, при компиляции библиотеки для двух TFM .NET Framework.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFrameworks>netstandard1.4;net40;net45</TargetFrameworks>
  </PropertyGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.0 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net40' ">
    <Reference Include="System.Net" />
  </ItemGroup>

  <!-- Conditionally obtain references for the .NET Framework 4.5 target -->
  <ItemGroup Condition=" '$(TargetFramework)' == 'net45' ">
    <Reference Include="System.Net.Http" />
    <Reference Include="System.Threading.Tasks" />
  </ItemGroup>

</Project>
```

В библиотеке или приложении следует написать условный код компиляции с помощью [директив препроцессора](../csharp/language-reference/preprocessor-directives/preprocessor-if.md) для каждой целевой платформы.

```csharp
public class MyClass
{
    static void Main()
    {
#if NET40
        Console.WriteLine("Target framework: .NET Framework 4.0");
#elif NET45
        Console.WriteLine("Target framework: .NET Framework 4.5");
#else
        Console.WriteLine("Target framework: .NET Standard 1.4");
#endif
    }
}
```

Система сборки учитывает символы препроцессора, представляющие целевые платформы, которые приведены в таблице [Поддерживаемые версии целевой платформы](#supported-target-frameworks), при использовании проектов в стиле SDK. При использовании символа, представляющего TFM .NET Standard, .NET Core или .NET 5, замените точки и дефисы символом подчеркивания и измените строчные буквы на прописные (например, символ для `netstandard1.4` — `NETSTANDARD1_4`).

Полный список символов препроцессора для целевой платформы .NET.

[!INCLUDE [Preprocessor symbols](../../includes/preprocessor-symbols.md)]

## <a name="deprecated-target-frameworks"></a>Неподдерживаемые целевые платформы

Следующие целевые платформы являются устаревшими. Пакеты, предназначенные для этих целевых платформ, следует перевести на предлагаемые для замены.

| Нерекомендуемый TFM                                                                             | Замена |
| ------------------------------------------------------------------------------------------ | ----------- |
| aspnet50<br>aspnetcore50<br>dnxcore50<br>dnx<br>dnx45<br>dnx451<br>dnx452                  | netcoreapp  |
| dotnet<br>dotnet50<br>dotnet51<br>dotnet52<br>dotnet53<br>dotnet54<br>dotnet55<br>dotnet56 | netstandard |
| netcore50                                                                                  | uap10.0     |
| win                                                                                        | netcore45   |
| win8                                                                                       | netcore45   |
| win81                                                                                      | netcore451  |
| win10                                                                                      | uap10.0     |
| winrt                                                                                      | netcore45   |

## <a name="see-also"></a>См. также раздел

- [Имена целевых платформ в .NET 5](https://github.com/dotnet/designs/blob/master/accepted/2020/net5/net5.md)
- [Разработка библиотек с помощью кроссплатформенных средств](../core/tutorials/libraries.md)
- [.NET Standard](net-standard.md)
- [Управление версиями .NET Core](../core/versions/index.md)
- [Репозиторий GitHub dotnet/standard](https://github.com/dotnet/standard)
- [Инструменты NuGet в репозитории GitHub](https://github.com/joelverhagen/NuGetTools)
- [Профили платформы в .NET](https://blog.stephencleary.com/2012/05/framework-profiles-in-net.html)
- [Анализатор совместимости платформ](analyzers/platform-compat-analyzer.md)
