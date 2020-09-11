---
ms.openlocfilehash: 6af63c0a58a3273aa98fa70f22e3637b481806b4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497307"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="98ddc-101">Более строгие проверки двоеточий в пути</span><span class="sxs-lookup"><span data-stu-id="98ddc-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="98ddc-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="98ddc-102">Details</span></span>

<span data-ttu-id="98ddc-103">В .NET Framework 4.6.2 выполнен ряд изменений для поддержки ранее не поддерживаемых путей (по длине и формату).</span><span class="sxs-lookup"><span data-stu-id="98ddc-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="98ddc-104">Исправлены проверки надлежащего синтаксиса разделителя диска (двоеточие), в результате появился побочный эффект в виде блокировки некоторых путей универсального кода ресурса (URI) в некоторых API-интерфейсах пути, где раньше это допускалось.</span><span class="sxs-lookup"><span data-stu-id="98ddc-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they were previously tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="98ddc-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="98ddc-105">Suggestion</span></span>

<span data-ttu-id="98ddc-106">При передаче универсального кода ресурса (URI) в соответствующий API сначала измените строку, чтобы она содержала допустимый путь.</span><span class="sxs-lookup"><span data-stu-id="98ddc-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span>

- <span data-ttu-id="98ddc-107">Удалите схему из URL-адресов вручную (например, удалите `file://` из URL-адресов).</span><span class="sxs-lookup"><span data-stu-id="98ddc-107">Remove the scheme from URLs manually (for example, remove `file://` from URLs).</span></span>

- <span data-ttu-id="98ddc-108">Передайте универсальный код ресурса (URI) в класс <xref:System.Uri> и используйте <xref:System.Uri.LocalPath>.</span><span class="sxs-lookup"><span data-stu-id="98ddc-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath>.</span></span>

<span data-ttu-id="98ddc-109">Кроме того, вы можете отказаться от новой нормализации путей, установив для переключателя `Switch.System.IO.UseLegacyPathHandling` AppContext значение `true`.</span><span class="sxs-lookup"><span data-stu-id="98ddc-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to `true`.</span></span>

| <span data-ttu-id="98ddc-110">Имя</span><span class="sxs-lookup"><span data-stu-id="98ddc-110">Name</span></span>    | <span data-ttu-id="98ddc-111">Значение</span><span class="sxs-lookup"><span data-stu-id="98ddc-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="98ddc-112">Область</span><span class="sxs-lookup"><span data-stu-id="98ddc-112">Scope</span></span>   | <span data-ttu-id="98ddc-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="98ddc-113">Edge</span></span>        |
| <span data-ttu-id="98ddc-114">Version</span><span class="sxs-lookup"><span data-stu-id="98ddc-114">Version</span></span> | <span data-ttu-id="98ddc-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="98ddc-115">4.6.2</span></span>       |
| <span data-ttu-id="98ddc-116">Type</span><span class="sxs-lookup"><span data-stu-id="98ddc-116">Type</span></span>    | <span data-ttu-id="98ddc-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="98ddc-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="98ddc-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="98ddc-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
