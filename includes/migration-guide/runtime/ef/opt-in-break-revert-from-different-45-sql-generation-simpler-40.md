---
ms.openlocfilehash: 22b5abbe769733e8d5ca3e78dd9e6e13b2363737
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620618"
---
### <a name="opt-in-break-to-revert-from-different-45-sql-generation-to-simpler-40-sql-generation"></a><span data-ttu-id="c97d9-101">Согласие на прерывание для возврата от генерируемого в версии 4.5 кода SQL к более простому коду, генерируемому в версии 4.0</span><span class="sxs-lookup"><span data-stu-id="c97d9-101">Opt-in break to revert from different 4.5 SQL generation to simpler 4.0 SQL generation</span></span>

#### <a name="details"></a><span data-ttu-id="c97d9-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c97d9-102">Details</span></span>

<span data-ttu-id="c97d9-103">Запросы, создающие операторы JOIN и содержащие вызов к операции ограничения без предварительного использования OrderBy, теперь создают более простой код SQL.</span><span class="sxs-lookup"><span data-stu-id="c97d9-103">Queries that produce JOIN statements and contain a call to a limiting operation without first using OrderBy now produce simpler SQL.</span></span> <span data-ttu-id="c97d9-104">После обновления до .NET Framework 4.5 эти запросы создают более сложный код SQL, чем предыдущие версии.</span><span class="sxs-lookup"><span data-stu-id="c97d9-104">After upgrading to .NET Framework 4.5, these queries produced more complicated SQL than previous versions.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c97d9-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="c97d9-105">Suggestion</span></span>

<span data-ttu-id="c97d9-106">Эта функция отключена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c97d9-106">This feature is disabled by default.</span></span> <span data-ttu-id="c97d9-107">Если Entity Framework создает лишние операторы JOIN, что ведет к ухудшению производительности, можно включить эту функцию, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения (app.config):</span><span class="sxs-lookup"><span data-stu-id="c97d9-107">If Entity Framework generates extra JOIN statements that cause performance degradation, you can enable this feature by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the application configuration (app.config) file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyLimitOperations&quot; value=&quot;true&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="c97d9-108">name</span><span class="sxs-lookup"><span data-stu-id="c97d9-108">Name</span></span>    | <span data-ttu-id="c97d9-109">Значение</span><span class="sxs-lookup"><span data-stu-id="c97d9-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c97d9-110">Область</span><span class="sxs-lookup"><span data-stu-id="c97d9-110">Scope</span></span>   |<span data-ttu-id="c97d9-111">Прозрачный</span><span class="sxs-lookup"><span data-stu-id="c97d9-111">Transparent</span></span>|
|<span data-ttu-id="c97d9-112">Version</span><span class="sxs-lookup"><span data-stu-id="c97d9-112">Version</span></span>|<span data-ttu-id="c97d9-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="c97d9-113">4.5.2</span></span>|
|<span data-ttu-id="c97d9-114">Type</span><span class="sxs-lookup"><span data-stu-id="c97d9-114">Type</span></span>|<span data-ttu-id="c97d9-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c97d9-115">Runtime</span></span>|
