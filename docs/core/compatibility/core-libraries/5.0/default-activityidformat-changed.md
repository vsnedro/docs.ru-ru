---
title: Критическое изменение. По умолчанию ActivityIdFormat имеет значение W3C
description: Ознакомьтесь с критическим изменением .NET 5.0 в основных библиотеках .NET, где ActivityIdFormat по умолчанию теперь имеет значение W3C.
ms.date: 11/01/2020
ms.openlocfilehash: 77ee705ac18065c84ddeab3127e01b6a40c3b84d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759835"
---
# <a name="default-activityidformat-is-w3c"></a>По умолчанию ActivityIdFormat имеет значение W3C

По умолчанию в качестве формата идентификатора действия (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) теперь используется <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.

## <a name="change-description"></a>Описание изменений

Формат идентификатора действия W3C был представлен в .NET Core 3.0 в качестве альтернативы иерархическому формату идентификатора. Тем не менее, чтобы обеспечить совместимость, вплоть до версии .NET 5.0 формат W3C не использовался по умолчанию. В .NET 5.0 значение по умолчанию было изменено в связи с [ратификацией формата W3C](https://www.w3.org/TR/trace-context/) для применения в различных реализациях языка.

Если ваше приложение предназначено не для платформы .NET 5.0 или более поздней версии, в нем будет применяться поведение предшествующих версий, в которых по умолчанию использовался формат <xref:System.Diagnostics.ActivityIdFormat.Hierarchical>. Это значение по умолчанию применяется для платформ net45+, netstandard1.1+ и netcoreapp (1.x, 2.x и 3.x). В .NET 5.0 и более поздних версий <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> имеет значение <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.

## <a name="version-introduced"></a>Представленная версия

5.0

## <a name="recommended-action"></a>Рекомендованное действие

Если в вашем приложении не используется идентификатор для распределенной трассировки, никаких действий не требуется. Такие библиотеки, как ASP.NET Core и <xref:System.Net.Http.HttpClient>, могут использовать и распространять обе версии <xref:System.Diagnostics.ActivityIdFormat>.

Если вам необходимо обеспечить совместимость с существующими системами, или в текущих системах учитывается формат идентификатора, вы можете сохранить старое поведение, установив для <xref:System.Diagnostics.Activity.DefaultIdFormat> значение <xref:System.Diagnostics.ActivityIdFormat.Hierarchical?displayProperty=nameWithType>. Кроме того, вы можете задать параметр AppContext одним из трех способов:

- В файле проекта.

  ```xml
  <ItemGroup>
    <RuntimeHostConfigurationOption Include="System.Diagnostics.DefaultActivityIdFormatIsHierarchial" Value="true" />
  </ItemGroup>
  ```

- В файле *runtimeconfig.json*.

  ```json
  {
      "runtimeOptions": {
          "configProperties": {
              "System.Diagnostics.DefaultActivityIdFormatIsHierarchial": true
          }
      }
  }
  ```

- С помощью переменной среды.

  Задайте для `DOTNET_SYSTEM_DIAGNOSTICS_DEFAULTACTIVITYIDFORMATISHIERARCHIAL` значение `true` или 1.

## <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
