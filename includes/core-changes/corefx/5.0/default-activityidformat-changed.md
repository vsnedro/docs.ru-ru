---
ms.openlocfilehash: d75dc2caa3a002b9d34ac74f2c5c5e192281c0df
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281314"
---
### <a name="default-activityidformat-is-w3c"></a>По умолчанию ActivityIdFormat имеет значение W3C

По умолчанию в качестве формата идентификатора действия (<xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType>) теперь используется <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.

#### <a name="change-description"></a>Описание изменений

Формат идентификатора действия W3C был представлен в .NET Core 3.0 в качестве альтернативы иерархическому формату идентификатора. Тем не менее, чтобы обеспечить совместимость, вплоть до версии .NET 5.0 формат W3C не использовался по умолчанию. В .NET 5.0 значение по умолчанию было изменено в связи с [ратификацией формата W3C](https://www.w3.org/TR/trace-context/) для применения в различных реализациях языка.

Если ваше приложение предназначено не для платформы .NET 5.0 или более поздней версии, в нем будет применяться поведение предшествующих версий, в которых по умолчанию использовался формат <xref:System.Diagnostics.ActivityIdFormat.Hierarchical>. Это значение по умолчанию применяется для платформ net45+, netstandard1.1+ и netcoreapp (1.x, 2.x и 3.x). В .NET 5.0 и более поздних версий <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=nameWithType> имеет значение <xref:System.Diagnostics.ActivityIdFormat.W3C?displayProperty=nameWithType>.

#### <a name="version-introduced"></a>Представленная версия

5.0 (предварительная версия 7)

#### <a name="recommended-action"></a>Рекомендованное действие

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

#### <a name="category"></a>Категория

Библиотеки Core .NET

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Diagnostics.Activity.DefaultIdFormat?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Diagnostics.Activity.DefaultIdFormat`

-->
