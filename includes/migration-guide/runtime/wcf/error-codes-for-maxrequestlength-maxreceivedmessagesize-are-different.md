---
ms.openlocfilehash: 26facb645de175d7ef0432394fc2b84f59e8437d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497357"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a>Коды ошибок для maxRequestLength или maxReceivedMessageSize различаются

#### <a name="details"></a>Подробнее

Если длина сообщений в веб-службах WCF, размещенных в службах IIS или на сервере ASP.NET Development Server, превышает maxRequestLength (в ASP.NET) или maxReceivedMessageSize (в WCF), им присваиваются разные коды ошибок. Код состояния HTTP изменился с 400 (неверный запрос) на 413 (слишком большая сущность запроса), а для сообщений, длина которых превышает maxRequestLength или maxReceivedMessageSize, теперь создается исключение <xref:System.ServiceModel.ProtocolException?displayProperty=fullName>. Сюда входят случаи, в которых режимом передачи является Streamed.

#### <a name="suggestion"></a>Предложение

Это изменение облегчает отладку в тех случаях, когда длина сообщения превышает ограничения, установленные ASP.NET или WCF. Необходимо внести изменения во весь код, который выполняет обработку на основании кода состояния HTTP 400.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.5|
|Type|Среда выполнения|

#### <a name="affected-apis"></a>Затронутые API

Невозможно обнаружить с помощью анализа API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
