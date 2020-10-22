---
ms.openlocfilehash: 1ddc2cea19872b44ff9659bcebd76117587ea89a
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159497"
---
### <a name="targetframework-change-from-netcoreapp-to-net"></a>Значение TargetFramework изменено с netcoreapp на net

Значение свойства MSBuild `TargetFramework` изменено с `netcoreapp3.1` на `net5.0`. Это может привести к ошибкам в коде, который основан на анализе значения `TargetFramework`.

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="change-description"></a>Описание изменений

В версиях .NET Core с 1.0 по 3.1 значение свойства MSBuild `TargetFramework` начинается с `netcoreapp`, например `netcoreapp3.1` для приложений, предназначенных для платформы .NET Core 3.1. Начиная с версии .NET 5.0 это значение упрощено и начинается с `net`, например `net5.0` для .NET 5.0.

Дополнительные сведения см. в разделе [Будущее .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) и [Имена целевых платформ в .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).

#### <a name="reason-for-change"></a>Причина изменения

- Упрощает значение `TargetFramework`.
- Позволяет включать `TargetPlatform` в свойство `TargetFramework` в проектах.

#### <a name="recommended-action"></a>Рекомендованное действие

Если вы используете логику, в которой выполняется синтаксический анализ значения `TargetFramework`, необходимо обновить ее. Например, в следующем условии MSBuild используется значение `TargetFramework`.

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

В соответствии с этим требованием можно обновить код, чтобы сравнить идентификатор целевой платформы.

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

#### <a name="category"></a>Категория

MSBuild

#### <a name="affected-apis"></a>Затронутые API

Н/Д

<!--

#### Affected APIs

Not detectable via API analysis.

-->
