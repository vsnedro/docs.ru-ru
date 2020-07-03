---
ms.openlocfilehash: 9a747d8fc15ca8fa2b915f89291f118d7344d172
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325226"
---
### <a name="httpsys-client-certificate-renegotiation-disabled-by-default"></a><span data-ttu-id="4e9b7-101">HttpSys: Повторное согласование сертификата клиента по умолчанию отключено</span><span class="sxs-lookup"><span data-stu-id="4e9b7-101">HttpSys: Client certificate renegotiation disabled by default</span></span>

<span data-ttu-id="4e9b7-102">Возможность повторного согласования подключения и запроса сертификата клиента по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-102">The option to renegotiate a connection and request a client certificate has been disabled by default.</span></span> <span data-ttu-id="4e9b7-103">Обсуждение этого вопроса см. на странице [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span><span class="sxs-lookup"><span data-stu-id="4e9b7-103">For discussion, see issue [dotnet/aspnetcore#23181](https://github.com/dotnet/aspnetcore/issues/23181).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="4e9b7-104">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="4e9b7-104">Version introduced</span></span>

<span data-ttu-id="4e9b7-105">ASP.NET Core 5.0</span><span class="sxs-lookup"><span data-stu-id="4e9b7-105">ASP.NET Core 5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="4e9b7-106">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="4e9b7-106">Old behavior</span></span>

<span data-ttu-id="4e9b7-107">Подключение можно повторно согласовать, чтобы запросить сертификат клиента.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-107">The connection can be renegotiated to request a client certificate.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="4e9b7-108">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="4e9b7-108">New behavior</span></span>

<span data-ttu-id="4e9b7-109">Сертификаты клиентов можно запросить только во время первоначального подтверждения соединения.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-109">Client certificates can only be requested during the initial connection handshake.</span></span> <span data-ttu-id="4e9b7-110">Подробную информацию см. в описании запроса на внесение изменений [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span><span class="sxs-lookup"><span data-stu-id="4e9b7-110">For more information, see pull request [dotnet/aspnetcore#23162](https://github.com/dotnet/aspnetcore/pull/23162).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="4e9b7-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="4e9b7-111">Reason for change</span></span>

<span data-ttu-id="4e9b7-112">Повторное согласование привело к ряду проблем с производительностью и взаимоблокировкой.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-112">Renegotiation caused a number of performance and deadlock issues.</span></span> <span data-ttu-id="4e9b7-113">Оно также не поддерживается в HTTP/2.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-113">It's also not supported in HTTP/2.</span></span> <span data-ttu-id="4e9b7-114">Расширенный контекст с момента реализации этого параметра для управления таким поведением в ASP.NET Core 3.1 см. на странице [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span><span class="sxs-lookup"><span data-stu-id="4e9b7-114">For additional context from when the option to control this behavior was introduced in ASP.NET Core 3.1, see issue [dotnet/aspnetcore#14806](https://github.com/dotnet/aspnetcore/issues/14806).</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="4e9b7-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="4e9b7-115">Recommended action</span></span>

<span data-ttu-id="4e9b7-116">Приложения, для которых требуются сертификаты клиентов, должны использовать *netsh.exe* для присвоения параметру `clientcertnegotiation` значения `enabled`.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-116">Apps that require client certificates should use *netsh.exe* to set the `clientcertnegotiation` option to `enabled`.</span></span> <span data-ttu-id="4e9b7-117">Дополнительные сведения см. в разделе [Команды netsh http](/windows-server/networking/technologies/netsh/netsh-http).</span><span class="sxs-lookup"><span data-stu-id="4e9b7-117">For more information, see [netsh http commands](/windows-server/networking/technologies/netsh/netsh-http).</span></span>

<span data-ttu-id="4e9b7-118">Если необходимо включить сертификаты клиентов только для некоторых частей приложения, см. инструкции в разделе [Дополнительные сертификаты клиента](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span><span class="sxs-lookup"><span data-stu-id="4e9b7-118">If you want client certificates enabled for only some parts of your app, see the guidance at [Optional client certificates](/aspnet/core/security/authentication/certauth?view=aspnetcore-3.1#optional-client-certificates).</span></span>

<span data-ttu-id="4e9b7-119">Если необходимо вернуть предыдущее поведение при повторном согласовании, задайте для `HttpSysOptions.ClientCertificateMethod` старое значение `ClientCertificateMethod.AllowRenegotiate`.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-119">If you need the old renegotiate behavior, set `HttpSysOptions.ClientCertificateMethod` to the old value `ClientCertificateMethod.AllowRenegotiate`.</span></span> <span data-ttu-id="4e9b7-120">Этот способ не рекомендуется по причинам, описанным выше и в соответствующем руководстве.</span><span class="sxs-lookup"><span data-stu-id="4e9b7-120">This isn't recommended for the reasons outlined above and in the linked guidance.</span></span>

#### <a name="category"></a><span data-ttu-id="4e9b7-121">Категория</span><span class="sxs-lookup"><span data-stu-id="4e9b7-121">Category</span></span>

<span data-ttu-id="4e9b7-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="4e9b7-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="4e9b7-123">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4e9b7-123">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync%2A?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.ClientCertificate`
- `Overload:Microsoft.AspNetCore.Http.ConnectionInfo.GetClientCertificateAsync`
- `Overload:Microsoft.AspNetCore.Server.HttpSys.HttpSysOptions.ClientCertificateMethod`

-->
