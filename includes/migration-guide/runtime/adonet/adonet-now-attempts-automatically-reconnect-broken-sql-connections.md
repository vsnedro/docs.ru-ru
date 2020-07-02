---
ms.openlocfilehash: 23ba6064a283b47312a66f3636c2834a7d58106e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620184"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="0461e-101">ADO.NET теперь пытается автоматически восстановить прерванное соединение SQL</span><span class="sxs-lookup"><span data-stu-id="0461e-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="0461e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0461e-102">Details</span></span>

<span data-ttu-id="0461e-103">Начиная с .NET Framework 4.5.1 .NET Framework будет пытаться автоматически восстанавливать прерванные соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="0461e-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="0461e-104">Хотя это повысит надежность приложений, существуют крайние случаи, в которых приложению должно быть известно, что соединение было потеряно, чтобы можно было выполнить определенное действие после восстановления подключения.</span><span class="sxs-lookup"><span data-stu-id="0461e-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0461e-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0461e-105">Suggestion</span></span>

<span data-ttu-id="0461e-106">Если эта функция нежелательна из-за проблем совместимости, ее можно отключить, установив для свойства <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> строки соединения (или <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) значение 0.</span><span class="sxs-lookup"><span data-stu-id="0461e-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="0461e-107">name</span><span class="sxs-lookup"><span data-stu-id="0461e-107">Name</span></span>    | <span data-ttu-id="0461e-108">Значение</span><span class="sxs-lookup"><span data-stu-id="0461e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0461e-109">Область</span><span class="sxs-lookup"><span data-stu-id="0461e-109">Scope</span></span>   |<span data-ttu-id="0461e-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="0461e-110">Edge</span></span>|
|<span data-ttu-id="0461e-111">Version</span><span class="sxs-lookup"><span data-stu-id="0461e-111">Version</span></span>|<span data-ttu-id="0461e-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0461e-112">4.5.1</span></span>|
|<span data-ttu-id="0461e-113">Type</span><span class="sxs-lookup"><span data-stu-id="0461e-113">Type</span></span>|<span data-ttu-id="0461e-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0461e-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0461e-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0461e-115">Affected APIs</span></span>

-<xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor></li><li><xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor></li><li><xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)></li></ul>|
