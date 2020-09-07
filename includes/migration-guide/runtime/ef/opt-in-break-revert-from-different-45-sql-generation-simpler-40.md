---
ms.openlocfilehash: 346fb6ecd43f7f93529e45f169c79b7acacc9c1f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496940"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="ca29a-101">Согласие на прерывание для возврата от генерируемого в версии 4.5 кода SQL к более простому коду, генерируемому в версии 4.0</span><span class="sxs-lookup"><span data-stu-id="ca29a-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="ca29a-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="ca29a-102">Details</span></span>

<span data-ttu-id="ca29a-103">Запросы, создающие операторы JOIN и содержащие вызов к операции ограничения без предварительного использования OrderBy, теперь создают более простой код SQL.</span><span class="sxs-lookup"><span data-stu-id="ca29a-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="ca29a-104">После обновления до .NET Framework 4.5 эти запросы создают более сложный код SQL, чем предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="ca29a-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="ca29a-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="ca29a-105">Suggestion</span></span>

<span data-ttu-id="ca29a-106">Эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ca29a-106">This feature is disabled by default.</span></span> <span data-ttu-id="ca29a-107">Если Entity Framework создает лишние операторы JOIN, что ведет к ухудшению производительности, можно включить эту функцию, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения (app.config):</span><span class="sxs-lookup"><span data-stu-id="ca29a-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="ca29a-108">name</span><span class="sxs-lookup"><span data-stu-id="ca29a-108">Name</span></span>    | <span data-ttu-id="ca29a-109">Значение</span><span class="sxs-lookup"><span data-stu-id="ca29a-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="ca29a-110">Область</span><span class="sxs-lookup"><span data-stu-id="ca29a-110">Scope</span></span>   |<span data-ttu-id="ca29a-111">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="ca29a-111">Transparent</span></span>|
|<span data-ttu-id="ca29a-112">Version</span><span class="sxs-lookup"><span data-stu-id="ca29a-112">Version</span></span>|<span data-ttu-id="ca29a-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="ca29a-113">4.5.2</span></span>|
|<span data-ttu-id="ca29a-114">Type</span><span class="sxs-lookup"><span data-stu-id="ca29a-114">Type</span></span>|<span data-ttu-id="ca29a-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="ca29a-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="ca29a-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="ca29a-116">Affected APIs</span></span>

<span data-ttu-id="ca29a-117">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="ca29a-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
