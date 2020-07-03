---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325226"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a>HttpSys: Повторное согласование сертификата клиента по умолчанию отключено

Возможность повторного согласования подключения и запроса сертификата клиента по умолчанию отключена. Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).

#### <a name="version-introduced"></a>Представленная версия

ASP.NET Core 5.0

#### <a name="old-behavior"></a>Старое поведение

Подключение можно повторно согласовать, чтобы запросить сертификат клиента.

#### <a name="new-behavior"></a>Новое поведение

Сертификаты клиентов можно запросить только во время первоначального подтверждения соединения. Подробную информацию см. в описании запроса на внесение изменений [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).

#### <a name="reason-for-change"></a>Причина изменения

Повторное согласование привело к ряду проблем с производительностью и взаимоблокировкой. Оно также не поддерживается в HTTP/2. Расширенный контекст с момента реализации этого параметра для управления таким поведением в ASP.NET Core 3.1 см. на странице [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).

#### <a name="recommended-action"></a>Рекомендованное действие

Приложения, для которых требуются сертификаты клиентов, должны использовать *netsh.exe* для присвоения параметру `clientcertnegotiation` значения `enabled`. Дополнительные сведения см. в разделе [Команды netsh http](/windows-server/networking/technologies/netsh/netsh-http).

Если необходимо включить сертификаты клиентов только для некоторых частей приложения, см. инструкции в разделе [Дополнительные сертификаты клиента](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).

Если необходимо вернуть предыдущее поведение при повторном согласовании, задайте для `HttpSysOptions.ClientCertificateMethod` старое значение `ClientCertificateMethod.AllowRenegotiate`. Этот способ не рекомендуется по причинам, описанным выше и в соответствующем руководстве.

#### <a name="category"></a>Категория

ASP.NET Core

#### <a name="affected-apis"></a>Затронутые API

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
