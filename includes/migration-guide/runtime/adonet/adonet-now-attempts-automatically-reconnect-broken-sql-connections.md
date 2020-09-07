---
ms.openlocfilehash: 7f7e718d543a4abdf2b8a87e52d8c0e2ba28203f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497933"
---
### <a name="adonet-now-attempts-to-automatically-reconnect-broken-sql-connections"></a><span data-ttu-id="0916e-101">ADO.NET теперь пытается автоматически восстановить прерванное соединение SQL</span><span class="sxs-lookup"><span data-stu-id="0916e-101">ADO.NET now attempts to automatically reconnect broken SQL connections</span></span>

#### <a name="details"></a><span data-ttu-id="0916e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0916e-102">Details</span></span>

<span data-ttu-id="0916e-103">Начиная с .NET Framework 4.5.1 .NET Framework будет пытаться автоматически восстанавливать прерванные соединения SQL.</span><span class="sxs-lookup"><span data-stu-id="0916e-103">Beginning in the .NET Framework 4.5.1, the .NET Framework will attempt to automatically reconnect broken SQL connections.</span></span> <span data-ttu-id="0916e-104">Хотя это повысит надежность приложений, существуют крайние случаи, в которых приложению должно быть известно, что соединение было потеряно, чтобы можно было выполнить определенное действие после восстановления подключения.</span><span class="sxs-lookup"><span data-stu-id="0916e-104">Although this will typically make apps more reliable, there are edge cases in which an app needs to know that the connection was lost so that it can take some action upon reconnection.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0916e-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0916e-105">Suggestion</span></span>

<span data-ttu-id="0916e-106">Если эта функция нежелательна из-за проблем совместимости, ее можно отключить, установив для свойства <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> строки соединения (или <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) значение 0.</span><span class="sxs-lookup"><span data-stu-id="0916e-106">If this feature is undesirable due to compatibility concerns, it can be disabled by setting the <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ConnectRetryCount?displayProperty=fullName> property of a connection string (or <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName>) to 0.</span></span>

| <span data-ttu-id="0916e-107">name</span><span class="sxs-lookup"><span data-stu-id="0916e-107">Name</span></span>    | <span data-ttu-id="0916e-108">Значение</span><span class="sxs-lookup"><span data-stu-id="0916e-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0916e-109">Область</span><span class="sxs-lookup"><span data-stu-id="0916e-109">Scope</span></span>   |<span data-ttu-id="0916e-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="0916e-110">Edge</span></span>|
|<span data-ttu-id="0916e-111">Version</span><span class="sxs-lookup"><span data-stu-id="0916e-111">Version</span></span>|<span data-ttu-id="0916e-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="0916e-112">4.5.1</span></span>|
|<span data-ttu-id="0916e-113">Type</span><span class="sxs-lookup"><span data-stu-id="0916e-113">Type</span></span>|<span data-ttu-id="0916e-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0916e-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0916e-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0916e-115">Affected APIs</span></span>

- <xref:System.Data.IDbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Configuration.ConnectionStringSettings.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnection.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.Common.DbConnectionStringBuilder.ConnectionString?displayProperty=nameWithType>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor>
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder.%23ctor(System.String)>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor>
- <xref:System.Data.Common.DbConnectionStringBuilder.%23ctor(System.Boolean)>

<!--

#### Affected APIs

- `P:System.Data.IDbConnection.ConnectionString`
- `P:System.Data.SqlClient.SqlConnection.ConnectionString`
- `P:System.Configuration.ConnectionStringSettings.ConnectionString`
- `P:System.Data.Common.DbConnection.ConnectionString`
- `P:System.Data.Common.DbConnectionStringBuilder.ConnectionString`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor`
- `M:System.Data.SqlClient.SqlConnectionStringBuilder.#ctor(System.String)`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor`
- `M:System.Data.Common.DbConnectionStringBuilder.#ctor(System.Boolean)`

-->
