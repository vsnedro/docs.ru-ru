---
ms.openlocfilehash: c996dafcf65b1fd428be908be346de603ead6e0b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615755"
---
### <a name="certificate-eku-oid-validation"></a>Проверка OID EKU сертификата

#### <a name="details"></a>Подробнее

Начиная с .NET Framework 4.6 классы <xref:System.Net.Security.SslStream> или <xref:System.Net.ServicePointManager> выполняют проверку идентификатора объекта (OID) расширенного использования ключа (EKU). Расширение расширенного использования ключа (EKU) — это коллекция идентификаторов объекта (OID), которые указывают приложения, использующие ключ. При проверке OID EKU используются обратные вызовы удаленного сертификата, чтобы у удаленного сертификата были правильные OID для указанных целей.

#### <a name="suggestion"></a>Предложение

Если это изменение нежелательно, можно отключить проверку OID EKU сертификата, добавив следующий параметр к [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) в файле конфигурации приложения:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontCheckCertificateEKUs=true" />
</runtime>
```

> [!IMPORTANT]
> Этот параметр предоставляется исключительно для обратной совместимости. Его использование в других целях не рекомендуется.

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.6         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.ServicePointManager?displayProperty=nameWithType>
- <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
