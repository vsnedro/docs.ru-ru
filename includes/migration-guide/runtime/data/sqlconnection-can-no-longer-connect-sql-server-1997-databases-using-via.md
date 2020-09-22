---
ms.openlocfilehash: e65ba0edb132f5cded244a69d58e43ffea76a039
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606902"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a><span data-ttu-id="13c98-101">SqlConnection больше не может подключаться к SQL Server 1997 или базам данных с помощью адаптера VIA</span><span class="sxs-lookup"><span data-stu-id="13c98-101">SqlConnection can no longer connect to SQL Server 1997 or databases using the VIA adapter</span></span>

#### <a name="details"></a><span data-ttu-id="13c98-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="13c98-102">Details</span></span>

<span data-ttu-id="13c98-103">Подключения к базам данных SQL Server с помощью [протокола Virtual Interface Adapter (VIA)](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) больше не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="13c98-103">Connections to SQL Server databases using the [Virtual Interface Adapter (VIA) protocol](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)) are no longer supported.</span></span> <span data-ttu-id="13c98-104">Протокол, используемый для подключения к базе данных SQL Server, отображается в строке подключения.</span><span class="sxs-lookup"><span data-stu-id="13c98-104">The protocol used to connect to a SQL Server database is visible in the connection string.</span></span> <span data-ttu-id="13c98-105">Для соединения VIA указано via:&lt;имя_сервера&gt;.</span><span class="sxs-lookup"><span data-stu-id="13c98-105">A VIA connection will contain via:&lt;servername&gt;.</span></span> <span data-ttu-id="13c98-106">Если это приложение подключается к SQL по протоколу, который отличается от VIA (например, tcp: или np:), критических изменений не будет.</span><span class="sxs-lookup"><span data-stu-id="13c98-106">If this app is connecting to SQL via a protocol other than VIA (tcp: or np: for example), then no breaking change will be encountered.</span></span> <span data-ttu-id="13c98-107">Также больше не поддерживаются подключения к SQL Server 7 (1997).</span><span class="sxs-lookup"><span data-stu-id="13c98-107">Also, connections to SQL Server 7 (1997) are no longer supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="13c98-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="13c98-108">Suggestion</span></span>

<span data-ttu-id="13c98-109">Не рекомендуется использовать протокол VIA. Выберите другой протокол для подключения к базам данных SQL.</span><span class="sxs-lookup"><span data-stu-id="13c98-109">The VIA protocol is deprecated, so an alternative protocol should be used to connect to SQL databases.</span></span> <span data-ttu-id="13c98-110">Обычно используется протокол TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="13c98-110">The most common protocol used is TCP/IP.</span></span> <span data-ttu-id="13c98-111">Дополнительные сведения см. в статье [Практическое руководство. Включение протокола TCP/IP для экземпляра базы данных](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="13c98-111">For more information about connecting through TCP/IP, see [Enable the TCP/IP protocol for a database instance](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)).</span></span> <span data-ttu-id="13c98-112">Если доступ к базе данных осуществляется только из интрасети, протокол общих каналов может обеспечить более высокую производительность, если сеть работает слишком медленно.</span><span class="sxs-lookup"><span data-stu-id="13c98-112">If the database is only accessed from within an intranet, the shared pipes protocol may provide better performance if the network is slow.</span></span>

| <span data-ttu-id="13c98-113">name</span><span class="sxs-lookup"><span data-stu-id="13c98-113">Name</span></span>    | <span data-ttu-id="13c98-114">Значение</span><span class="sxs-lookup"><span data-stu-id="13c98-114">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="13c98-115">Область</span><span class="sxs-lookup"><span data-stu-id="13c98-115">Scope</span></span>   |<span data-ttu-id="13c98-116">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="13c98-116">Edge</span></span>|
|<span data-ttu-id="13c98-117">Version</span><span class="sxs-lookup"><span data-stu-id="13c98-117">Version</span></span>|<span data-ttu-id="13c98-118">4.5</span><span class="sxs-lookup"><span data-stu-id="13c98-118">4.5</span></span>|
|<span data-ttu-id="13c98-119">Type</span><span class="sxs-lookup"><span data-stu-id="13c98-119">Type</span></span>|<span data-ttu-id="13c98-120">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="13c98-120">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="13c98-121">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="13c98-121">Affected APIs</span></span>

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
