---
ms.openlocfilehash: 5b566dd89801caff7a253abc2fb62c5fd79591f7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606535"
---
### <a name="sslstream-supports-tls-alerts"></a><span data-ttu-id="37513-101">SslStream поддерживает TLS оповещения</span><span class="sxs-lookup"><span data-stu-id="37513-101">SslStream supports TLS Alerts</span></span>

#### <a name="details"></a><span data-ttu-id="37513-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="37513-102">Details</span></span>

<span data-ttu-id="37513-103">После сбоя подтверждения TLS при первой операции ввода-вывода чтения и записи возникнет <xref:System.IO.IOException?displayProperty=fullName> с внутренним исключением <xref:System.ComponentModel.Win32Exception?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="37513-103">After a failed TLS handshake, an <xref:System.IO.IOException?displayProperty=fullName> with an inner <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> exception will be thrown by the first I/O Read/Write operation.</span></span> <span data-ttu-id="37513-104">Код <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> для <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> может сопоставляться с оповещением TLS от удаленной стороны с помощью [кодов ошибок Schannel для оповещений TLS и SSL](/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts). Дополнительные сведения см. в [RFC 2246: Раздел 7.2.2 Предупреждения об ошибках](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span><span class="sxs-lookup"><span data-stu-id="37513-104">The <xref:System.ComponentModel.Win32Exception.NativeErrorCode?displayProperty=fullName> code for the <xref:System.ComponentModel.Win32Exception?displayProperty=fullName> can be mapped to the TLS Alert from the remote party using the [Schannel error codes for TLS and SSL alerts](/windows/desktop/SecAuthN/schannel-error-codes-for-tls-and-ssl-alerts).For more information, see [RFC 2246: Section 7.2.2 Error alerts](https://tools.ietf.org/html/rfc2246#section-7.2.2).</span></span> <br/><span data-ttu-id="37513-105">Этот режим в .NET Framework 4.6.2 и более ранних версий предполагает, что время ожидания канала транспорта (как правило, TCP-подключения) истечет во время операции записи или чтения, если другой стороне не удалось выполнить подтверждение и она сразу же после этого отклонила подключение.</span><span class="sxs-lookup"><span data-stu-id="37513-105">The behavior in .NET Framework 4.6.2 and earlier is that the transport channel (usually TCP connection) will timeout during either Write or Read if the other party failed the handshake and immediately afterwards rejected the connection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="37513-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="37513-106">Suggestion</span></span>

<span data-ttu-id="37513-107">Приложения, вызывающие API сетевого ввода-вывода, такие как <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)>, должны обрабатывать <xref:System.IO.IOException> или <xref:System.TimeoutException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="37513-107">Applications calling network I/O APIs such as <xref:System.IO.Stream.Read(System.Byte[],System.Int32,System.Int32)>/<xref:System.IO.Stream.Write(System.Byte[],System.Int32,System.Int32)> should handle <xref:System.IO.IOException> or <xref:System.TimeoutException?displayProperty=fullName>.</span></span><br/><span data-ttu-id="37513-108">Начиная с .NET Framework 4.7 функция оповещений TLS включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="37513-108">The TLS Alerts feature is enabled by default starting with .NET Framework 4.7.</span></span> <span data-ttu-id="37513-109">Для приложений, предназначенных для версий платформы .NET Framework с 4.0 по 4.6.2, работающих в системе .NET Framework 4.7 или более поздних версий, эта функция будет отключена для сохранения совместимости.</span><span class="sxs-lookup"><span data-stu-id="37513-109">Applications targeting versions of the .NET Framework from 4.0 through 4.6.2 running on a .NET Framework 4.7 or higher system will have the feature disabled to preserve compatibility.</span></span> <br/><span data-ttu-id="37513-110">Следующий API конфигурации можно использовать для включения или отключения этой функции для приложений .NET Framework 4.6 и более поздних версий, работающих в среде .NET Framework 4.7 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="37513-110">The following configuration API is available to enable or disable the feature for .NET Framework 4.6 and later applications running on .NET Framework 4.7 or later.</span></span>

- <span data-ttu-id="37513-111">Программное выполнение:   Это должно быть первым, что делает приложение, поскольку ServicePointManager будет инициализироваться только один раз:</span><span class="sxs-lookup"><span data-stu-id="37513-111">Programmatically:   Must be the very first thing the application does since ServicePointManager will initialize only once:</span></span>

    ```csharp
    AppContext.SetSwitch("TestSwitch.LocalAppContext.DisableCaching", true);

    // Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2.
    AppContext.SetSwitch("Switch.System.Net.DontEnableTlsAlerts", true);
    ```

- <span data-ttu-id="37513-112">AppConfig:</span><span class="sxs-lookup"><span data-stu-id="37513-112">AppConfig:</span></span>

    ```xml
    <runtime>
      <AppContextSwitchOverrides value="Switch.System.Net.DontEnableTlsAlerts=true"/>
      <!-- Set to 'false' to enable the feature in .NET Framework 4.6 - 4.6.2. -->
    </runtime>
    ```

- <span data-ttu-id="37513-113">Раздел реестра (глобальный):   Установите значение `false`, чтобы включить эту функцию в .NET Framework 4.6–4.6.2.</span><span class="sxs-lookup"><span data-stu-id="37513-113">Registry key (machine global):   Set the Value to `false` to enable the feature in .NET Framework 4.6 - 4.6.2.</span></span>

    ```ini
    Key: HKLM\SOFTWARE\Wow6432Node\Microsoft\.NETFramework\AppContext\Switch.System.Net.DontEnableTlsAlerts
    - Type: String
    - Value: "true"
    ```

| <span data-ttu-id="37513-114">name</span><span class="sxs-lookup"><span data-stu-id="37513-114">Name</span></span>    | <span data-ttu-id="37513-115">Значение</span><span class="sxs-lookup"><span data-stu-id="37513-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="37513-116">Область</span><span class="sxs-lookup"><span data-stu-id="37513-116">Scope</span></span>   | <span data-ttu-id="37513-117">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="37513-117">Edge</span></span>        |
| <span data-ttu-id="37513-118">Version</span><span class="sxs-lookup"><span data-stu-id="37513-118">Version</span></span> | <span data-ttu-id="37513-119">4.7</span><span class="sxs-lookup"><span data-stu-id="37513-119">4.7</span></span>         |
| <span data-ttu-id="37513-120">Type</span><span class="sxs-lookup"><span data-stu-id="37513-120">Type</span></span>    | <span data-ttu-id="37513-121">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="37513-121">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="37513-122">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="37513-122">Affected APIs</span></span>

- <xref:System.Net.Security.SslStream?displayProperty=nameWithType>
- <xref:System.Net.WebRequest?displayProperty=nameWithType>
- <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.FtpWebRequest?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- <xref:System.Net.Http?displayProperty=nameWithType>
