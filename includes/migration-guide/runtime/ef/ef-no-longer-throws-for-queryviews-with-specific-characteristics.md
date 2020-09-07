---
ms.openlocfilehash: ceae6b85c14862b1b1183d01def0dda723ee0c2b
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497600"
---
### <a name="ef-no-longer-throws-for-queryviews-with-specific-characteristics"></a><span data-ttu-id="bf1e4-101">EF более не создает исключения для представлений QueryView с определенными характеристиками</span><span class="sxs-lookup"><span data-stu-id="bf1e4-101">EF no longer throws for QueryViews with specific characteristics</span></span>

#### <a name="details"></a><span data-ttu-id="bf1e4-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="bf1e4-102">Details</span></span>

<span data-ttu-id="bf1e4-103">Entity Framework больше не создает исключение <xref:System.StackOverflowException?displayProperty=fullName>, если приложение выполняет запрос, включающий представление QueryView со свойством навигации 0..1, которое пытается включить связанные объекты в запрос.</span><span class="sxs-lookup"><span data-stu-id="bf1e4-103">Entity Framework no longer throws a <xref:System.StackOverflowException?displayProperty=fullName> exception when an app executes a query that involves a QueryView with a 0..1 navigation property that attempts to include the related entities as part of the query.</span></span> <span data-ttu-id="bf1e4-104">Например, это могло быть сделано путем вызова <code>.Include(e =&gt; e.RelatedNavProp)</code>.</span><span class="sxs-lookup"><span data-stu-id="bf1e4-104">For example, by calling <code>.Include(e =&gt; e.RelatedNavProp)</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="bf1e4-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="bf1e4-105">Suggestion</span></span>

<span data-ttu-id="bf1e4-106">Это изменение влияет только на код, использующий представления QueryView с отношениями 1-0..1 при выполнении запросов, вызывающих метод .Include.</span><span class="sxs-lookup"><span data-stu-id="bf1e4-106">This change only affects code that uses QueryViews with 1-0..1 relationships when running queries that call .Include.</span></span> <span data-ttu-id="bf1e4-107">Эта функция повышает надежность и должна быть прозрачна почти для всех приложений.</span><span class="sxs-lookup"><span data-stu-id="bf1e4-107">It improves reliability and should be transparent to almost all apps.</span></span> <span data-ttu-id="bf1e4-108">Тем не менее, если она вызывает непредвиденное поведение, ее можно отключить, добавив следующую запись в раздел <code>&lt;appSettings&gt;</code> файла конфигурации приложения:</span><span class="sxs-lookup"><span data-stu-id="bf1e4-108">However, if it causes unexpected behavior, you can disable it by adding the following entry to the <code>&lt;appSettings&gt;</code> section of the app's configuration file:</span></span><pre><code class="lang-xml">&lt;add key=&quot;EntityFramework_SimplifyUserSpecifiedViews&quot; value=&quot;false&quot; /&gt;&#13;&#10;</code></pre>

| <span data-ttu-id="bf1e4-109">name</span><span class="sxs-lookup"><span data-stu-id="bf1e4-109">Name</span></span>    | <span data-ttu-id="bf1e4-110">Значение</span><span class="sxs-lookup"><span data-stu-id="bf1e4-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="bf1e4-111">Область</span><span class="sxs-lookup"><span data-stu-id="bf1e4-111">Scope</span></span>   |<span data-ttu-id="bf1e4-112">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="bf1e4-112">Edge</span></span>|
|<span data-ttu-id="bf1e4-113">Version</span><span class="sxs-lookup"><span data-stu-id="bf1e4-113">Version</span></span>|<span data-ttu-id="bf1e4-114">4.5.2</span><span class="sxs-lookup"><span data-stu-id="bf1e4-114">4.5.2</span></span>|
|<span data-ttu-id="bf1e4-115">Type</span><span class="sxs-lookup"><span data-stu-id="bf1e4-115">Type</span></span>|<span data-ttu-id="bf1e4-116">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="bf1e4-116">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="bf1e4-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="bf1e4-117">Affected APIs</span></span>

<span data-ttu-id="bf1e4-118">Невозможно обнаружить с помощью анализа API.</span><span class="sxs-lookup"><span data-stu-id="bf1e4-118">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
