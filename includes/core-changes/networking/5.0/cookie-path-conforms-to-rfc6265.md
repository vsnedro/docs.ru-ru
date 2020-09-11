---
ms.openlocfilehash: 7140f6d4cac063088b3663ab98d292104218b542
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465521"
---
### <a name="cookie-path-handling-now-conforms-to-rfc-6265"></a>Алгоритмы обработки путей класса Cookie приведены в соответствие с RFC 6265

Алгоритмы обработки путей, определенные в [RFC 6265](https://tools.ietf.org/html/rfc6265), реализованы для классов <xref:System.Net.Cookie> и <xref:System.Net.CookieContainer>.

#### <a name="version-introduced"></a>Представленная версия

5.0

#### <a name="change-description"></a>Описание изменений

- Свойство <xref:System.Net.Cookie.Path> больше не должно быть префиксом пути запроса.
- Вычисление значения по умолчанию для <xref:System.Net.Cookie.Path> и алгоритмов сопоставления путей реализовано в RFC 6265 в [разделе 5.1.4](https://tools.ietf.org/html/rfc6265#section-5.1.4).

#### <a name="recommended-action"></a>Рекомендуемое действие

В большинстве случаев вам не нужно предпринимать никаких действий. Но если код зависел от проверки <xref:System.Net.Cookie.Path>, вам нужно реализовать необходимую проверку в коде. Если код зависел от вычисления значения по умолчанию для <xref:System.Net.Cookie.Path>, попробуйте вручную указать значение <xref:System.Net.Cookie.Path>, а не использовать значение по умолчанию.

#### <a name="category"></a>Категория

Сети

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Cookie?displayProperty=fullName>
- <xref:System.Net.CookieContainer?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Net.Cookie`
- `T:System.Net.CookieContainer`

-->
