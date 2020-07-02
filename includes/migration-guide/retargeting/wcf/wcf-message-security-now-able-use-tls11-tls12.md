---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614804"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a>Для безопасности сообщений WCF теперь могут использоваться TLS1.1 и TLS1.2

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.7 клиенты могут настроить в параметрах конфигурации приложения не только SSL3.0 и TLS1.0, но и TLS1.1 или TLS1.2.

#### <a name="suggestion"></a>Предложение

В .NET Framework 4.7 поддержка TLS1.1 и TLS1.2 в безопасности сообщений WCF по умолчанию отключена. Вы можете включить ее, добавив следующую строку в раздел `<runtime>` файла app.config или web.config:

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7         |
| Type    | Изменение целевой платформы |
