---
ms.openlocfilehash: bbeca87b3f498213b91d942cc4f197c9d80457a8
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497328"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="f47ed-101">Попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с `localhost`, завершается ошибкой</span><span class="sxs-lookup"><span data-stu-id="f47ed-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="f47ed-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="f47ed-102">Details</span></span>

<span data-ttu-id="f47ed-103">В .NET Framework 4.6 и 4.6.1 попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с <code>localhost</code>, завершается ошибкой: &quot;При установлении подключения к SQL Server произошла ошибка сети или ошибка экземпляра.</span><span class="sxs-lookup"><span data-stu-id="f47ed-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="f47ed-104">Сервер не найден или недоступен.</span><span class="sxs-lookup"><span data-stu-id="f47ed-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="f47ed-105">Проверьте правильность имени экземпляра и настройку сервера SQL Server для удаленных подключений.</span><span class="sxs-lookup"><span data-stu-id="f47ed-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="f47ed-106">(поставщик: сетевые интерфейсы SQL, ошибка: 26 — ошибка при обнаружении указанного сервера или экземпляра)&quot;</span><span class="sxs-lookup"><span data-stu-id="f47ed-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f47ed-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="f47ed-107">Suggestion</span></span>

<span data-ttu-id="f47ed-108">Эта проблема устранена, и восстановлено прежнее поведение в .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="f47ed-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="f47ed-109">Для подключения к базе данных SQL Server, которой сопоставляется <code>localhost</code>, выполните обновление до .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="f47ed-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="f47ed-110">name</span><span class="sxs-lookup"><span data-stu-id="f47ed-110">Name</span></span>    | <span data-ttu-id="f47ed-111">Значение</span><span class="sxs-lookup"><span data-stu-id="f47ed-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f47ed-112">Область</span><span class="sxs-lookup"><span data-stu-id="f47ed-112">Scope</span></span>   |<span data-ttu-id="f47ed-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="f47ed-113">Minor</span></span>|
|<span data-ttu-id="f47ed-114">Version</span><span class="sxs-lookup"><span data-stu-id="f47ed-114">Version</span></span>|<span data-ttu-id="f47ed-115">4.6</span><span class="sxs-lookup"><span data-stu-id="f47ed-115">4.6</span></span>|
|<span data-ttu-id="f47ed-116">Type</span><span class="sxs-lookup"><span data-stu-id="f47ed-116">Type</span></span>|<span data-ttu-id="f47ed-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="f47ed-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="f47ed-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="f47ed-118">Affected APIs</span></span>

<span data-ttu-id="f47ed-119">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="f47ed-119">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
