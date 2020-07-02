---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621215"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a>Удаление Ssl3 из WCF TransportDefaults

#### <a name="details"></a>Подробнее

При использовании NetTcp для обеспечения безопасности транспорта и применении типа учетных данных сертификата протокол SSL 3 больше не является протоколом по умолчанию для согласования безопасного соединения. В большинстве случаев существующие приложения не должны затрагиваться, так как протокол TLS 1.0 всегда входил в список протоколов для NetTcp. Все существующие клиенты должны иметь возможность согласовывать подключение с помощью TLS версии не ниже 1.0.

#### <a name="suggestion"></a>Предложение

Если требуется Ssl3, воспользуйтесь одним из указанных ниже механизмов конфигурации и добавьте Ssl3 в список установленных протоколов.<ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li>[Раздел &lt;sslStreamSecurity&gt;&lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</li></ul>

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6.2|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
