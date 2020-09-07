---
ms.openlocfilehash: 0d38e2177377e7e9ea911071eb65aa13aa1f5900
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496425"
---
### <a name="dataannotationsdatatypeattributedisableregex-app-setting-is-on-by-default-in-net-framework-472"></a>Параметр приложения "dataAnnotations:dataTypeAttribute:disableRegEx" по умолчанию включен в .NET Framework 4.7.2

#### <a name="details"></a>Подробнее

В .NET Framework 4.6.1 появился новый параметр приложения (<code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code>), который позволяет пользователям отключать регулярные выражения в атрибутах типов данных (таких как <xref:System.ComponentModel.DataAnnotations.EmailAddressAttribute?displayProperty=nameWithType>, <xref:System.ComponentModel.DataAnnotations.UrlAttribute?displayProperty=nameWithType> и <xref:System.ComponentModel.DataAnnotations.PhoneAttribute?displayProperty=nameWithType>). Это помогает сделать приложения менее уязвимыми, в частности для атак типа "отказ в обслуживании" с использованием определенных регулярных выражений.<br/>В .NET Framework 4.6.1 этот параметр, запрещающий использование RegEx, по умолчанию имел значение <code>false</code>. Начиная с версии .NET Framework 4.7.2, эта настройка по умолчанию переведена в значение <code>true</code>. Это обеспечивает дополнительную защиту от уязвимостей для приложений, разрабатываемых с использованием .NET Framework 4.7.2.

#### <a name="suggestion"></a>Предложение

Если после перехода на версию .NET Framework 4.7.2 вы обнаружите, что регулярные выражения в вашем веб-приложении перестали работать, вы можете изменить значение <code>&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot;</code> на <code>false</code> и вернуться к предыдущему режиму работы.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;appSettings&gt;&#13;&#10;...&#13;&#10;&lt;add key=&quot;dataAnnotations:dataTypeAttribute:disableRegEx&quot; value=&quot;false&quot;/&gt;&#13;&#10;...&#13;&#10;&lt;/appSettings&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.7.2|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
