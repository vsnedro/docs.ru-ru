---
ms.openlocfilehash: 8dc947f584d3433f0638a72f4db86ac2680c8dbf
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497153"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="352e3-101">SqlConnection больше не может подключаться к SQL Server 1997 или базам данных с помощью адаптера VIA</span><span class="sxs-lookup"><span data-stu-id="352e3-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="352e3-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="352e3-102">Details</span></span>

<span data-ttu-id="352e3-103">Подключения к базам данных SQL Server с помощью [протокола Virtual Interface Adapter (VIA)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="352e3-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="352e3-104">Протокол, используемый для подключения к базе данных SQL Server, отображается в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="352e3-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="352e3-105">Для соединения VIA указано via:&lt;имя_сервера&gt;.</span><span class="sxs-lookup"><span data-stu-id="352e3-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="352e3-106">Если это приложение подключается к SQL по протоколу, который отличается от VIA (например, tcp: или np:), критических изменений не будет.</span><span class="sxs-lookup"><span data-stu-id="352e3-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="352e3-107">Также больше не поддерживаются подключения к SQL Server 7 (1997).</span><span class="sxs-lookup"><span data-stu-id="352e3-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="352e3-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="352e3-108">Suggestion</span></span>

<span data-ttu-id="352e3-109">Не рекомендуется использовать протокол VIA. Выберите другой протокол для подключения к базам данных SQL.</span><span class="sxs-lookup"><span data-stu-id="352e3-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="352e3-110">Обычно используется протокол TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="352e3-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="352e3-111">Дополнительные сведения см. в статье [Практическое руководство. Включение протокола TCP/IP для экземпляра базы данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="352e3-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="352e3-112">Если доступ к базе данных осуществляется только из интрасети, протокол общих каналов может обеспечить более высокую производительность, если сеть работает слишком медленно.</span><span class="sxs-lookup"><span data-stu-id="352e3-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="352e3-113">name</span><span class="sxs-lookup"><span data-stu-id="352e3-113">Name</span></span>    | <span data-ttu-id="352e3-114">Значение</span><span class="sxs-lookup"><span data-stu-id="352e3-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="352e3-115">Область</span><span class="sxs-lookup"><span data-stu-id="352e3-115">Scope</span></span>   |<span data-ttu-id="352e3-116">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="352e3-116">Edge</span></span>|
|<span data-ttu-id="352e3-117">Version</span><span class="sxs-lookup"><span data-stu-id="352e3-117">Version</span></span>|<span data-ttu-id="352e3-118">4.5</span><span class="sxs-lookup"><span data-stu-id="352e3-118">4.5</span></span>|
|<span data-ttu-id="352e3-119">Type</span><span class="sxs-lookup"><span data-stu-id="352e3-119">Type</span></span>|<span data-ttu-id="352e3-120">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="352e3-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="352e3-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="352e3-121">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
