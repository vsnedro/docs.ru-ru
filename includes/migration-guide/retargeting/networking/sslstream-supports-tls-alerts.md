---
ms.openlocfilehash: 0024b2a53444319788b8cdd312d537f994070b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614760"
---
### <a name="sslstream-supports-tls-alerts"></a>SslStream поддерживает TLS оповещения

#### <a name="details"></a>Подробнее

После сбоя подтверждения TLS при первой операции ввода-вывода чтения и записи возникнет <xref:System.IO.IOException?displayProperty=fullName> с внутренним исключением <xref:System.ComponentModel.Win32Exception?displayProperty=fullName>. Код <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> для <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> может сопоставляться с оповещением TLS от удаленной стороны с помощью [кодов ошибок Schannel для оповещений TLS и SSL](https://docs.microsoft.com/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts). Дополнительные сведения см. в [RFC 2246: Раздел 7.2.2 Предупреждения об ошибках](https://tools.ietf.org/html/rfc2246#section-7.2.2). <br/>Этот режим в .NET Framework 4.6.2 и более ранних версий предполагает, что время ожидания канала транспорта (как правило, TCP-подключения) истечет во время операции записи или чтения, если другой стороне не удалось выполнить подтверждение и она сразу же после этого отклонила подключение.

#### <a name="suggestion"></a>Предложение

Приложения, вызывающие API сетевого ввода-вывода, такие как <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>, должны обрабатывать <xref:System.IO.IOException> или <xref:System.TimeoutException?displayProperty=fullName>.<br/>Начиная с .NET Framework 4.7 функция оповещений TLS включена по умолчанию. Для приложений, предназначенных для версий платформы .NET Framework с 4.0 по 4.6.2, работающих в системе .NET Framework 4.7 или более поздних версий, эта функция будет отключена для сохранения совместимости. <br/>Следующий API конфигурации можно использовать для включения или отключения этой функции для приложений .NET Framework 4.6 и более поздних версий, работающих в среде .NET Framework 4.7 или более поздней версии.

- Программное выполнение:   Это должно быть первым, что делает приложение, поскольку ServicePointManager будет инициализироваться только один раз:

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- AppConfig:

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- Раздел реестра (глобальный):   Установите значение `false`, чтобы включить эту функцию в .NET Framework 4.6–4.6.2.

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| name    | Значение       |
|:--------|:------------|
| Область   | Пограничный случай        |
| Version | 4.7         |
| Type    | Изменение целевой платформы |

#### <a name="affected-apis"></a>Затронутые API

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
