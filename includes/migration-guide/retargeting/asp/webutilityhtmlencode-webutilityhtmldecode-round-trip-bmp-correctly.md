---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617259"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a>WebUtility.HtmlEncode и WebUtility.HtmlDecode корректно совершают круговой путь в BMP

#### <a name="details"></a>Подробнее

Для приложений, предназначенных для .NET Framework 4.5, символы, не входящие в базовый многоязыковый набор кодировок (BMP), правильно передаются в оба конца, если они передаются методам <xref:System.Net.WebUtility.HtmlDecode(System.String)>.

#### <a name="suggestion"></a>Предложение

Это изменение не должно влиять на текущие приложения, но для восстановления исходного поведения задайте атрибут `targetFramework` элемента `<httpRuntime>` для строки, отличный от "4.5". Также можно задать атрибуты `unicodeEncodingConformance` и `unicodeDecodingConformance` элемента конфигурации `<webUtility>`, чтобы контролировать это поведение вне зависимости от целевой версии .NET Framework.

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.5         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
