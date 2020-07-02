---
ms.openlocfilehash: d587e542a72d584502ac3ac892619cc38b88ef77
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620147"
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
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.HttpUtility.JavaScriptStringEncode(System.String,System.Boolean)?displayProperty=nameWithType></li></ul>|
