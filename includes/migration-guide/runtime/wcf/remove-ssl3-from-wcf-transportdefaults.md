---
ms.openlocfilehash: a5f4047d70276a90c9d72918a2559fd795feb26e
ms.sourcegitcommit: 261e0c98a111357692b3b63c596edf0cacf72991
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "90770895"
---
### <a name="remove-ssl3-from-the-wcf-transportdefaults"></a><span data-ttu-id="abcbf-101">Удаление Ssl3 из WCF TransportDefaults</span><span class="sxs-lookup"><span data-stu-id="abcbf-101">Remove Ssl3 from the WCF TransportDefaults</span></span>

#### <a name="details"></a><span data-ttu-id="abcbf-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="abcbf-102">Details</span></span>

<span data-ttu-id="abcbf-103">При использовании NetTcp для обеспечения безопасности транспорта и применении типа учетных данных сертификата протокол SSL 3 больше не является протоколом по умолчанию для согласования безопасного соединения.</span><span class="sxs-lookup"><span data-stu-id="abcbf-103">When using NetTcp with transport security and a credential type of certificate, the SSL 3 protocol is no longer a default protocol used for negotiating a secure connection.</span></span> <span data-ttu-id="abcbf-104">В большинстве случаев существующие приложения не должны затрагиваться, так как протокол TLS 1.0 всегда входил в список протоколов для NetTcp.</span><span class="sxs-lookup"><span data-stu-id="abcbf-104">In most cases there should be no impact to existing apps as TLS 1.0 has always been included in the protocol list for NetTcp.</span></span> <span data-ttu-id="abcbf-105">Все существующие клиенты должны иметь возможность согласовывать подключение с помощью TLS версии не ниже 1.0.</span><span class="sxs-lookup"><span data-stu-id="abcbf-105">All existing clients should be able to negotiate a connection using at least TLS1.0.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="abcbf-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="abcbf-106">Suggestion</span></span>

<span data-ttu-id="abcbf-107">Если требуется Ssl3, воспользуйтесь одним из указанных ниже механизмов конфигурации и добавьте Ssl3 в список установленных протоколов.</span><span class="sxs-lookup"><span data-stu-id="abcbf-107">If Ssl3 is required, use one of the following configuration mechanisms to add Ssl3 to the list of negotiated protocols.</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>
- [<span data-ttu-id="abcbf-108">\<transport> из \<netTcpBinding></span><span class="sxs-lookup"><span data-stu-id="abcbf-108">\<transport> of \<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-nettcpbinding.md)
- [\<sslStreamSecurity>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md)

| <span data-ttu-id="abcbf-109">Имя</span><span class="sxs-lookup"><span data-stu-id="abcbf-109">Name</span></span>    | <span data-ttu-id="abcbf-110">Значение</span><span class="sxs-lookup"><span data-stu-id="abcbf-110">Value</span></span>   |
|:--------|:--------|
| <span data-ttu-id="abcbf-111">Область</span><span class="sxs-lookup"><span data-stu-id="abcbf-111">Scope</span></span>   | <span data-ttu-id="abcbf-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="abcbf-112">Edge</span></span>    |
| <span data-ttu-id="abcbf-113">Version</span><span class="sxs-lookup"><span data-stu-id="abcbf-113">Version</span></span> | <span data-ttu-id="abcbf-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="abcbf-114">4.6.2</span></span>   |
| <span data-ttu-id="abcbf-115">Type</span><span class="sxs-lookup"><span data-stu-id="abcbf-115">Type</span></span>    | <span data-ttu-id="abcbf-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="abcbf-116">Runtime</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="abcbf-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="abcbf-117">Affected APIs</span></span>

- <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols?displayProperty=nameWithType>
- <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols`
- `P:System.ServiceModel.TcpTransportSecurity.SslProtocols`

-->
