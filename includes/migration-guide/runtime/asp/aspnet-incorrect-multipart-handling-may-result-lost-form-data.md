---
ms.openlocfilehash: ed669364efe9dd8f57d831a3764dd3fc68cd5e05
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496692"
---
### <a name="aspnet-incorrect-multipart-handling-may-result-in-lost-form-data"></a>Неправильная составная обработка ASP.NET может привести к потере данных формы.

#### <a name="details"></a>Подробнее

В приложениях, предназначенных для .NET Framework 4.7.2 и более ранних версий, ASP.Net может неправильно выполнять синтаксический анализ составных граничных значений, и это приведет к тому, что данные формы будут недоступны во время выполнения запроса. Приложения, предназначенные для .NET Framework 4.8 или более поздних версий, правильно выполняют синтаксический анализ составных данных, поэтому значения формы доступны во время выполнения запроса.

#### <a name="suggestion"></a>Предложение

Начиная с приложений, выполняемых на .NET Framework 4.8, при нацеливании на .NET Framework 4.8 или более поздней версии с помощью элемента <code>targetFrameworkVersion</code> поведение по умолчанию меняется на удаление разделителей. При нацеливании на предыдущие версии платформы или если <code>targetFrameworkVersion</code> не используется, конечные разделители для некоторых значений по-прежнему возвращаются. Этим поведением можно также явно управлять при помощи <code>appSetting</code>:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;aspnet:UseLegacyMultiValueHeaderHandling&quot;  value=&quot;true&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Неизвестно|
|Version|4.8|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.HttpRequest.Form?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.Files?displayProperty=nameWithType>
- <xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.HttpRequest.Form`
- `P:System.Web.HttpRequest.Files`
- `P:System.Web.HttpRequest.ContentEncoding`

-->
