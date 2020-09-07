---
ms.openlocfilehash: ef3114a4eb9f62030c3ec36d3b463d07ccd59f6d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496219"
---
### <a name="webutilityhtmldecode-no-longer-decodes-invalid-input-sequences"></a>Метод WebUtility.HtmlDecode больше не декодирует недопустимую входную последовательность

#### <a name="details"></a>Подробнее

По умолчанию методы декодирования больше не декодируют недопустимую входную последовательность в недопустимую строку UTF-16. Вместо этого они возвращают исходные входные данные.

#### <a name="suggestion"></a>Предложение

Изменение в выходных данных декодера может иметь значение, только если в строках хранятся двоичные данные, а не данные UTF-16. Чтобы явно контролировать это поведение, присвойте атрибуту <code>aspnet:AllowRelaxedUnicodeDecoding</code> элемента [appSettings](~/docs/framework/configure-apps/file-schema/appsettings/index.md) значение <code>true</code>, чтобы разрешить устаревшее поведение, или значение <code>false</code>, чтобы разрешить текущее поведение.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.5|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.WebUtility.HtmlDecode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.UrlDecode(System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.WebUtility.HtmlDecode(System.String)`
- `M:System.Net.WebUtility.HtmlDecode(System.String,System.IO.TextWriter)`
- `M:System.Net.WebUtility.UrlDecode(System.String)`

-->
