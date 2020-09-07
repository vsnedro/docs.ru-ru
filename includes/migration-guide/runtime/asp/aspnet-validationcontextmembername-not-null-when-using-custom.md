---
ms.openlocfilehash: 904a6abee2b4b2cf2f5727fb70e286c8a1a592c4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496867"
---
### <a name="aspnet-validationcontextmembername-is-not-null-when-using-custom-dataannotationsvalidationattribute"></a>ASP.NET ValidationContext.MemberName не имеет значения NULL при использовании пользовательского DataAnnotations.ValidationAttribute

#### <a name="details"></a>Подробнее

В .NET Framework 4.7.2 и более ранних версий при использовании пользовательского <xref:System.ComponentModel.DataAnnotations.ValidationAttribute?displayProperty=nameWithType> свойство <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType> возвращает `null`. В версии .NET Framework 4.8 до обновления October 2019 возвращает имя элемента. Начиная с версии [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) для .NET Framework 4.8 возвращает `null` по умолчанию, но при этом сохраняется возможность вернуть имя элемента.

#### <a name="suggestion"></a>Предложение

Добавьте следующий параметр в файл *web.config* для свойства, чтобы вернуть имя элемента в [.NET Framework October 2019 Preview of Quality Rollup](https://devblogs.microsoft.com/dotnet/net-framework-october-2019-preview-of-quality-rollup/) для .NET Framework 4.8 и более поздних версий:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:GetValidationMemberName&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>В версии .NET Framework 4.8 до обновления October 2019, добавление этого параметра в файл *web.config* восстанавливает предыдущее поведение, а свойство возвращает `null`.

| name    | Значение       |
|:--------|:------------|
| Область   |Неизвестно|
|Version|4.8|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.ComponentModel.DataAnnotations.ValidationContext.MemberName?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ComponentModel.DataAnnotations.ValidationContext.MemberName`

-->
