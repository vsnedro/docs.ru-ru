---
ms.openlocfilehash: 29908ed916690e67db3cc5d72ebe1b1c6aea45c6
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325202"
---
### <a name="iis-urlrewrite-middleware-query-strings-are-preserved"></a>IIS. Строки запросов ПО промежуточного слоя UrlRewrite сохраняются

Ошибки в ПО промежуточного слоя IIS UrlRewrite не позволили сохранить строку запроса в правиле перезаписи. Эта ошибка исправлена, чтобы обеспечить соответствие поведению модуля IIS UrlRewrite.

Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#22972](https://github.com/dotnet/aspnetcore/issues/22972).

#### <a name="version-introduced"></a>Представленная версия

ASP.NET Core 5.0 (предварительная версия 7)

#### <a name="old-behavior"></a>Старое поведение

Рассмотрим следующее правило перезаписи.

```xml
<rule name="MyRule" stopProcessing="true">
  <match url="^about" />
  <action type="Redirect" url="/contact" redirectType="Temporary" appendQueryString="true" />
</rule>
```

Предыдущее правило не присоединяет строку запроса. Универсальный код ресурса (URI), такой как `/about?id=1`, перенаправляет в `/contact` вместо `/contact?id=1`. По умолчанию атрибут `appendQueryString` имеет значение `true`.

#### <a name="new-behavior"></a>Новое поведение

Строка запроса сохраняется. Код URI из примера в разделе [Старое поведение](#old-behavior) будет иметь значение `/contact?id=1`.

#### <a name="reason-for-change"></a>Причина изменения

Старое поведение не соответствовало поведению модуля IIS UrlRewrite. Для поддержки переноса между ПО промежуточного слоя и модулем важно обеспечить согласованное поведение.

#### <a name="recommended-action"></a>Рекомендованное действие

Если удаление строки запроса является предпочтительным поведением, следует установить для элемента `action` значение `appendQueryString="false"`.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

<xref:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

`Overload:Microsoft.AspNetCore.Rewrite.IISUrlRewriteOptionsExtensions.AddIISUrlRewrite`

-->
