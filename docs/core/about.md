---
title: Обзор .NET Core
description: Сведения о характеристиках и компоновке .NET Core, а также ее сравнение с другими реализациями .NET.
ms.date: 03/26/2020
ms.openlocfilehash: e57451968ed8c4d5457acea084d3c6c9f998b8da
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144530"
---
# <a name="net-core-overview"></a>Обзор .NET Core

.NET Core обладает следующими характеристиками:

- **Кроcсплатформенность.** Поддержка [операционных систем](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) Windows, macOS и Linux.
- **Открытый код.** Платформа .NET Core базируется [на открытом коде](https://github.com/dotnet/core) и распространяется по лицензиям MIT и Apache 2. .NET Core является проектом [.NET Foundation](https://dotnetfoundation.org/).
- **Современные технологии.** В ней реализованы современные парадигмы, такие как асинхронное программирование, шаблоны без копирования с использованием структур и управление ресурсами для контейнеров.
- **Производительность.**  Обеспечивает [высокую производительность](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-core-3-0/) за счет таких возможностей, как [встроенные аппаратные компоненты](https://devblogs.microsoft.com/dotnet/hardware-intrinsics-in-net-core/), [многоуровневая компиляция](https://github.com/dotnet/coreclr/blob/master/Documentation/design-docs/tiered-compilation.md) и [Span\<T>](../standard/memory-and-spans/index.md).
- **Согласованность между средами.** Одинаковое выполнение кода в различных операционных системах и архитектурах, включая x64, x86 и ARM.
- **Программы командной строки.**  Удобные средства командной строки для локальной разработки и непрерывной интеграции.
- **Гибкая разработка.** .NET Core можно включить в приложение или установить параллельно (на уровне пользователя или системы). Возможность использования с [контейнерами Docker](docker/introduction.md).

## <a name="languages"></a>Языки

Языки [C#](../csharp/index.yml), [Visual Basic](../visual-basic/index.yml) и [F#](../fsharp/index.yml) можно использовать для создания приложений и библиотек для .NET Core. Эти языки можно использовать в вашем любимом текстовом редакторе либо интегрированной среде разработки (IDE), включая следующие.

- [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)
- [Visual Studio Code](https://code.visualstudio.com/download)

Интеграция редактора возможна во многом благодаря участникам проектов [OmniSharp](https://www.omnisharp.net/) и [Ionide](https://ionide.io).

## <a name="apis"></a>API - интерфейсы

.NET Core предоставляет платформы для создания приложений любого типа:

* разработка облачных приложений с помощью [ASP.NET Core](/aspnet/core/);
* разработка мобильных приложений с помощью [Xamarin](/xamarin);
* разработка приложений для Интернета вещей с помощью [System.Device.GPIO](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0);
* разработка клиентских приложений Windows с помощью [WPF](../desktop-wpf/overview/index.md) и Windows Forms;
* машинное обучение с помощью [ML.NET](../machine-learning/index.yml).

Включены многие API общего назначения, например:

- Примитивные типы, например <xref:System.Boolean?displayProperty=nameWithType> и <xref:System.Int32?displayProperty=nameWithType>.
- Коллекции, такие как <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> и <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>.
- Служебные типы, такие как <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> и <xref:System.IO.FileStream?displayProperty=nameWithType>.
- Типы данных, такие как <xref:System.Data.DataSet?displayProperty=nameWithType> и <xref:System.Data.Entity.DbSet?displayProperty=nameWithType>.
- Высокопроизводительные типы, такие как <xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Numerics.Vector?displayProperty=nameWithType> и [Pipelines](../standard/io/pipelines.md).

Благодаря поддержке спецификации [.NET Standard](../standard/net-standard.md) платформа .NET Core совместима с .NET Framework и API-интерфейсами Mono.

## <a name="composition"></a>Композиция

.NET Core состоит из перечисленных ниже компонентов.

- [Среда выполнения .NET Core](https://github.com/dotnet/runtime/tree/master/src/coreclr) предоставляет систему типов, функции загрузки сборок, сборщик мусора, собственные функции взаимодействия и другие базовые службы. [Библиотеки платформы .NET Core](https://github.com/dotnet/runtime/tree/master/src/libraries) предоставляют примитивные типы данных, типы компоновки приложений и базовые служебные программы.
- [Среда выполнения ASP.NET Core](https://github.com/dotnet/aspnetcore) — это платформа для создания современных облачных приложений, подключенных к Интернету: веб-приложений, приложений Интернета вещей, серверной части мобильных решений и многого другого.
- [.NET Core CLI](https://github.com/dotnet/sdk) и компиляторы языков ([Roslyn](https://github.com/dotnet/roslyn) и [F#](https://github.com/microsoft/visualfsharp)) реализуют возможности разработки .NET Core.
- [Команда dotnet](./tools/dotnet.md) используется для запуска приложений .NET Core и CLI. Оно выбирает и размещает среду выполнения, предоставляет политику загрузки сборок и запускает приложения и инструменты.

### <a name="open-source"></a>Открытый код

[.NET Core](about.md) — это платформа разработки общего назначения с [открытым кодом](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT), предназначенная для создания кроссплатформенных приложений. Вы можете создавать приложения .NET Core для Windows, macOS и Linux с поддержкой процессоров x64, x86, ARM32 и ARM64. Вам доступны платформы и API-интерфейсы для создания [облачных](/aspnet/core/) приложений, приложений для [Интернета вещей](https://docs.microsoft.com/archive/msdn-magazine/2019/august/net-core-cross-platform-iot-programming-with-net-core-3-0), использования [клиентского интерфейса](../desktop-wpf/overview/index.md) и [машинного обучения](../machine-learning/index.yml).

## <a name="support"></a>Поддержка

[Корпорация Майкрософт](https://dotnet.microsoft.com/platform/support/policy) реализует поддержку платформы .NET Core для операционных систем Windows, macOS и Linux. Она регулярно обновляется для обеспечения безопасности и качества (второй вторник каждого месяца).

Двоичные дистрибутивы .NET Core от Майкрософт собираются и тестируются в Azure на серверах Майкрософт и следуют методикам проектирования и безопасности Майкрософт.

[Red Hat поддерживает .NET Core](https://developers.redhat.com/topics/dotnet/) в операционной системе Red Hat Enterprise Linux (RHEL). Red Hat собирает .NET Core из исходного кода и публикует сборки на сайте [Red Hat Software Collections](https://developers.redhat.com/products/softwarecollections/overview/). Red Hat и Майкрософт совместно занимаются обеспечением беспроблемной работы .NET Core в RHEL.

[Tizen поддерживает .NET Core](https://developer.tizen.org/development/training/.net-application) на платформах Tizen.
