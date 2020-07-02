---
ms.openlocfilehash: 87cb2570d3d47a2acb85b5557141c0fef885516a
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621820"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="22360-101">Попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с `localhost`, завершается ошибкой</span><span class="sxs-lookup"><span data-stu-id="22360-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

#### <a name="details"></a><span data-ttu-id="22360-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="22360-102">Details</span></span>

<span data-ttu-id="22360-103">В .NET Framework 4.6 и 4.6.1 попытка подключения TCP/IP к базе данных SQL Server, которая сопоставляется с <code>localhost</code>, завершается ошибкой: &quot;При установлении подключения к SQL Server произошла ошибка сети или ошибка экземпляра.</span><span class="sxs-lookup"><span data-stu-id="22360-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="22360-104">Сервер не найден или недоступен.</span><span class="sxs-lookup"><span data-stu-id="22360-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="22360-105">Проверьте правильность имени экземпляра и настройку сервера SQL Server для удаленных подключений.</span><span class="sxs-lookup"><span data-stu-id="22360-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="22360-106">(поставщик: сетевые интерфейсы SQL, ошибка: 26 — ошибка при обнаружении указанного сервера или экземпляра)&quot;</span><span class="sxs-lookup"><span data-stu-id="22360-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>

#### <a name="suggestion"></a><span data-ttu-id="22360-107">Предложение</span><span class="sxs-lookup"><span data-stu-id="22360-107">Suggestion</span></span>

<span data-ttu-id="22360-108">Эта проблема устранена, и восстановлено прежнее поведение в .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="22360-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="22360-109">Для подключения к базе данных SQL Server, которой сопоставляется <code>localhost</code>, выполните обновление до .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="22360-109">To connect to a SQL Server database that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>

| <span data-ttu-id="22360-110">name</span><span class="sxs-lookup"><span data-stu-id="22360-110">Name</span></span>    | <span data-ttu-id="22360-111">Значение</span><span class="sxs-lookup"><span data-stu-id="22360-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="22360-112">Область</span><span class="sxs-lookup"><span data-stu-id="22360-112">Scope</span></span>   |<span data-ttu-id="22360-113">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="22360-113">Minor</span></span>|
|<span data-ttu-id="22360-114">Version</span><span class="sxs-lookup"><span data-stu-id="22360-114">Version</span></span>|<span data-ttu-id="22360-115">4.6</span><span class="sxs-lookup"><span data-stu-id="22360-115">4.6</span></span>|
|<span data-ttu-id="22360-116">Type</span><span class="sxs-lookup"><span data-stu-id="22360-116">Type</span></span>|<span data-ttu-id="22360-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="22360-117">Runtime</span></span>|
