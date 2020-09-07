---
ms.openlocfilehash: 12fb72d5ee9fc0d6c57899589cb2b0da7db41f4a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496584"
---
### <a name="httputilityjavascriptstringencode-escapes-ampersand"></a>Метод HttpUtility.JavaScriptStringEncode экранирует символ амперсанда

#### <a name="details"></a>Подробнее

Начиная с версии .NET Framework 4.5, метод <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=fullName> экранирует символ амперсанда (&amp;).

#### <a name="suggestion"></a>Предложение

Если в приложении предполагается прежнее поведение данного метода, можно добавить параметр aspnet:JavaScriptDoNotEncodeAmpersand в [элемент appSettings ASP.NET](https://docs.microsoft.com/previous-versions/aspnet/hh975440(v=vs.120)) в файле конфигурации.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String)`
- `M:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)`

-->
