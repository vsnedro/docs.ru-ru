---
ms.openlocfilehash: 5c86be598ab6196ecf4da05451c7f22d2be52c12
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614700"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>Значение по умолчанию ServicePointManager.SecurityProtocol — SecurityProtocolType.System.Default

#### <a name="details"></a>Подробнее

Начиная с приложений, ориентированных на .NET Framework 4.7, свойство <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> имеет значение <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Это изменение позволяет сетевым API-интерфейсам .NET Framework на основе SslStream (таких как FTP, HTTPS и SMTP) наследовать протоколы безопасности по умолчанию из операционной системы вместо использования жестко запрограммированных значений, определенных в .NET Framework. Значение по умолчанию зависит от операционной системы и пользовательской настройки, выполненной системным администратором. Сведения о протоколе SChannel по умолчанию в каждой версии операционной системы Windows см. в разделе [Протоколы TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).</p>В приложениях, предназначенных для более ранних версий платформы .NET Framework, значение по умолчанию свойства <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> зависит от версии целевой платформы .NET Framework. Дополнительные сведения см. в разделе [Изменение целевой платформы для миграции с .NET Framework 4.5.2 на 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking).

#### <a name="suggestion"></a>Предложение

Это изменение касается только приложений, предназначенных для .NET Framework 4.7 или более поздних версий. Если вы предпочитаете использовать определенный протокол, а не полагаться на параметры системы по умолчанию, можно явно задать значение свойства <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>. Если такое изменение нежелательно, от него можно отказаться, добавив параметр конфигурации в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. В следующем примере показан как раздел `<runtime>`, так и параметр отключения `Switch.System.Net.DontEnableSystemDefaultTlsVersions`:

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSystemDefaultTlsVersions=true" />
</runtime>
```

| name    | Значение       |
|:--------|:------------|
| Область   | Дополнительный номер       |
| Version | 4.7         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>
