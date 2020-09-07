---
ms.openlocfilehash: 4394e69dafeb6cce2d7719a67bbce396d3bc1086
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497259"
---
### <a name="wpf-datatemplate-elements-are-now-visible-to-uia"></a><span data-ttu-id="6463b-101">Элементы WPF DataTemplate теперь отображаются в UIA</span><span class="sxs-lookup"><span data-stu-id="6463b-101">WPF DataTemplate elements are now visible to UIA</span></span>

#### <a name="details"></a><span data-ttu-id="6463b-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="6463b-102">Details</span></span>

<span data-ttu-id="6463b-103">Ранее элементы <xref:System.Windows.DataTemplate?displayProperty=fullName> не отображались в службе автоматизации пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6463b-103">Previously, <xref:System.Windows.DataTemplate?displayProperty=fullName> elements were invisible to UI Automation.</span></span> <span data-ttu-id="6463b-104">Начиная с версии 4.5, служба автоматизации пользовательского интерфейса будет обнаруживать эти элементы.</span><span class="sxs-lookup"><span data-stu-id="6463b-104">Beginning in 4.5, UI Automation will detect these elements.</span></span> <span data-ttu-id="6463b-105">Это полезно во многих случаях, но может нарушить выполнение тестов, зависящих от деревьев UIA, не содержащих элементы <xref:System.Windows.DataTemplate?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6463b-105">This is useful in many cases, but can break tests that depend on UIA trees not containing <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6463b-106">Предложение</span><span class="sxs-lookup"><span data-stu-id="6463b-106">Suggestion</span></span>

<span data-ttu-id="6463b-107">Тесты службы автоматизации пользовательского интерфейса для этого приложения может потребоваться обновить с учетом того, что теперь дерево UIA содержит ранее невидимые элементы <xref:System.Windows.DataTemplate?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="6463b-107">UI Automation tests for this app may need updated to account for the UIA tree now including previously invisible <xref:System.Windows.DataTemplate?displayProperty=fullName> elements.</span></span> <span data-ttu-id="6463b-108">Например, тесты, которые ожидают, что некоторые элементы находятся рядом друг с другом, теперь могут ожидать, что между ними располагаются ранее невидимые элементы UIA.</span><span class="sxs-lookup"><span data-stu-id="6463b-108">For example, tests that expect some elements to be next to each other may now need to expect previously invisible UIA elements in between.</span></span> <span data-ttu-id="6463b-109">Или может потребоваться обновить новыми значениями тесты, которые зависят от определенных количеств или индексов для UIA элементов.</span><span class="sxs-lookup"><span data-stu-id="6463b-109">Or tests that rely on certain counts or indexes for UIA elements may need updated with new values.</span></span>

| <span data-ttu-id="6463b-110">name</span><span class="sxs-lookup"><span data-stu-id="6463b-110">Name</span></span>    | <span data-ttu-id="6463b-111">Значение</span><span class="sxs-lookup"><span data-stu-id="6463b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6463b-112">Область</span><span class="sxs-lookup"><span data-stu-id="6463b-112">Scope</span></span>   |<span data-ttu-id="6463b-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="6463b-113">Edge</span></span>|
|<span data-ttu-id="6463b-114">Version</span><span class="sxs-lookup"><span data-stu-id="6463b-114">Version</span></span>|<span data-ttu-id="6463b-115">4.5</span><span class="sxs-lookup"><span data-stu-id="6463b-115">4.5</span></span>|
|<span data-ttu-id="6463b-116">Type</span><span class="sxs-lookup"><span data-stu-id="6463b-116">Type</span></span>|<span data-ttu-id="6463b-117">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="6463b-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6463b-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="6463b-118">Affected APIs</span></span>

- <xref:System.Windows.DataTemplate.%23ctor>
- <xref:System.Windows.DataTemplate.%23ctor(System.Object)>

<!--

#### Affected APIs

- `M:System.Windows.DataTemplate.#ctor`
- `M:System.Windows.DataTemplate.#ctor(System.Object)`

-->
