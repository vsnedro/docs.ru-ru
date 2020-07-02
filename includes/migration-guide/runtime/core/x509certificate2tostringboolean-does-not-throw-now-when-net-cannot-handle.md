---
ms.openlocfilehash: 51208762cea2a5688c5d43e5d444d4e014e5f0b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621427"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a>Теперь метод X509Certificate2.ToString(Boolean) не создает исключение, когда .NET не удается обработать сертификат

#### <a name="details"></a>Подробнее

В .NET Framework 4.5.2 и более ранних версиях этот метод создавал исключение, если значение <code>true</code> передавалось в параметр verbose и были установлены сертификаты, не поддерживаемые .NET Framework. Теперь метод будет выполняться успешно и возвращать допустимую строку, в которой пропущены недоступные части сертификата.

#### <a name="suggestion"></a>Предложение

Любой код, зависящий от <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>, следует обновить для ожидания того, что в некоторых случаях, когда ранее API возвращал исключение, в возвращаемой строке могут отсутствовать некоторые данные сертификата (например, открытый ключ, закрытый ключ и расширения).

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|
