---
ms.openlocfilehash: 9b734fe960165b6d4b97b861cb3e8f31979f25c5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621215"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="7eb2f-101">Удаление Ssl3 из WCF TransportDefaults</span><span class="sxs-lookup"><span data-stu-id="7eb2f-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="7eb2f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="7eb2f-102">Details</span></span>

<span data-ttu-id="7eb2f-103">При использовании NetTcp для обеспечения безопасности транспорта и применении типа учетных данных сертификата протокол SSL 3 больше не является протоколом по умолчанию для согласования безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="7eb2f-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="7eb2f-104">В большинстве случаев существующие приложения не должны затрагиваться, так как протокол TLS 1.0 всегда входил в список протоколов для NetTcp.</span><span class="sxs-lookup"><span data-stu-id="7eb2f-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="7eb2f-105">Все существующие клиенты должны иметь возможность согласовывать подключение с помощью TLS версии не ниже 1.0.</span><span class="sxs-lookup"><span data-stu-id="7eb2f-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="7eb2f-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="7eb2f-106">Suggestion</span></span>

<span data-ttu-id="7eb2f-107">Если требуется Ssl3, воспользуйтесь одним из указанных ниже механизмов конфигурации и добавьте Ssl3 в список установленных протоколов.</span><span class="sxs-lookup"><span data-stu-id="7eb2f-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span><ul><li><xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols></li><li>[<](~/docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)</li><li><span data-ttu-id="7eb2f-108">[Раздел &lt;sslStreamSecurity&gt;&lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span><span class="sxs-lookup"><span data-stu-id="7eb2f-108">[&lt;sslStreamSecurity&gt; section of &lt;customBinding&gt;]~/docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)</span></span></li></ul>

| <span data-ttu-id="7eb2f-109">name</span><span class="sxs-lookup"><span data-stu-id="7eb2f-109">Name</span></span>    | <span data-ttu-id="7eb2f-110">Значение</span><span class="sxs-lookup"><span data-stu-id="7eb2f-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="7eb2f-111">Область</span><span class="sxs-lookup"><span data-stu-id="7eb2f-111">Scope</span></span>   |<span data-ttu-id="7eb2f-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="7eb2f-112">Edge</span></span>|
|<span data-ttu-id="7eb2f-113">Version</span><span class="sxs-lookup"><span data-stu-id="7eb2f-113">Version</span></span>|<span data-ttu-id="7eb2f-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="7eb2f-114">4.6.2</span></span>|
|<span data-ttu-id="7eb2f-115">Type</span><span class="sxs-lookup"><span data-stu-id="7eb2f-115">Type</span></span>|<span data-ttu-id="7eb2f-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="7eb2f-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7eb2f-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="7eb2f-117">Affected APIs</span></span>

-<xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType></li><li><xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType></li></ul>|
