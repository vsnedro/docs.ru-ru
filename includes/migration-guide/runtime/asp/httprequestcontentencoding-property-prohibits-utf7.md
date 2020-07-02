---
ms.openlocfilehash: 7d3568fef933758c40e47cefa86c24d31d4119fc
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620135"
---
### <a name="httprequestcontentencoding-property-prohibits-utf7"></a>Свойство HttpRequest.ContentEncoding запрещает кодировку UTF7

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.5 кодировка UTF-7 запрещена в теле <xref:System.Web.HttpRequest?displayProperty=fullName>. Данные для приложений, которые зависят от поступающих данных UTF-7, в некоторых случаях декодируются неверно.

#### <a name="suggestion"></a>Предложение

В идеальном случае приложения необходимо обновить, чтобы они не использовали кодировку UTF-7 в <xref:System.Web.HttpRequest?displayProperty=fullName>. Кроме того, устаревшее поведение можно восстановить с помощью атрибута <code>aspnet:AllowUtf7RequestContentEncoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/appsettings-element-for-configuration.md).

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Web.HttpRequest.ContentEncoding?displayProperty=nameWithType></li></ul>|
