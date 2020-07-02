---
ms.openlocfilehash: 768a948849064cedb38110f5ed271717442325c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620619"
---
### <a name="log-file-name-created-by-the-objectcontextcreatedatabase-method-has-changed-to-match-sql-server-specifications"></a><span data-ttu-id="0974f-101">Имя файла журнала, созданного методом ObjectContext.CreateDatabase, изменилось в соответствии со спецификациями SQL Server</span><span class="sxs-lookup"><span data-stu-id="0974f-101">Log file name created by the ObjectContext.CreateDatabase method has changed to match SQL Server specifications</span></span>

#### <a name="details"></a><span data-ttu-id="0974f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="0974f-102">Details</span></span>

<span data-ttu-id="0974f-103">При вызове метода <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> либо напрямую, либо с использованием Code First с поставщиком SqlClient и значения AttachDBFilename в строке подключения он создает файл журнала с именем filename_log.ldf вместо filename.ldf (где filename — имя файла, заданное значением AttachDBFilename).</span><span class="sxs-lookup"><span data-stu-id="0974f-103">When the <xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=fullName> method is called either directly or by using Code First with the SqlClient provider and an AttachDBFilename value in the connection string, it creates a log file named filename_log.ldf instead of filename.ldf (where filename is the name of the file specified by the AttachDBFilename value).</span></span> <span data-ttu-id="0974f-104">Это изменение улучшает отладку, предоставляя файл журнала, имя которого соответствует спецификациям SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0974f-104">This change improves debugging by providing a log file named according to SQL Server specifications.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0974f-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="0974f-105">Suggestion</span></span>

<span data-ttu-id="0974f-106">Если имя файла журнала важно для приложения, приложение следует обновить для использования стандартного формата имени файла _log.ldf.</span><span class="sxs-lookup"><span data-stu-id="0974f-106">If the log file name is important for an app, the app should be updated to expect the standard _log.ldf file name format.</span></span>

| <span data-ttu-id="0974f-107">name</span><span class="sxs-lookup"><span data-stu-id="0974f-107">Name</span></span>    | <span data-ttu-id="0974f-108">Значение</span><span class="sxs-lookup"><span data-stu-id="0974f-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0974f-109">Область</span><span class="sxs-lookup"><span data-stu-id="0974f-109">Scope</span></span>   |<span data-ttu-id="0974f-110">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="0974f-110">Edge</span></span>|
|<span data-ttu-id="0974f-111">Version</span><span class="sxs-lookup"><span data-stu-id="0974f-111">Version</span></span>|<span data-ttu-id="0974f-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0974f-112">4.5</span></span>|
|<span data-ttu-id="0974f-113">Type</span><span class="sxs-lookup"><span data-stu-id="0974f-113">Type</span></span>|<span data-ttu-id="0974f-114">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="0974f-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0974f-115">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="0974f-115">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li></ul>|
