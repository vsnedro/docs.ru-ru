---
ms.openlocfilehash: 3e4a5936bbac4e77efc5f7e68b55ddf49bae5d43
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614717"
---
### <a name="path-colon-checks-are-stricter"></a><span data-ttu-id="d5296-101">Более строгие проверки двоеточий в пути</span><span class="sxs-lookup"><span data-stu-id="d5296-101">Path colon checks are stricter</span></span>

#### <a name="details"></a><span data-ttu-id="d5296-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d5296-102">Details</span></span>

<span data-ttu-id="d5296-103">В .NET Framework 4.6.2 выполнен ряд изменений для поддержки ранее не поддерживаемых путей (по длине и формату).</span><span class="sxs-lookup"><span data-stu-id="d5296-103">In .NET Framework 4.6.2, a number of changes were made to support previously unsupported paths (both in length and format).</span></span> <span data-ttu-id="d5296-104">Исправлены проверки надлежащего синтаксиса разделителя диска (двоеточие), в результате появился побочный эффект в виде блокировки некоторых путей универсального кода ресурса (URI) в некоторых API-интерфейсах пути, где раньше это допускалось.</span><span class="sxs-lookup"><span data-stu-id="d5296-104">Checks for proper drive separator (colon) syntax were made more correct, which had the side effect of blocking some URI paths in a few select Path APIs where they used to be tolerated.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d5296-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="d5296-105">Suggestion</span></span>

<span data-ttu-id="d5296-106">При передаче универсального кода ресурса (URI) в соответствующий API сначала измените строку, чтобы она содержала допустимый путь.</span><span class="sxs-lookup"><span data-stu-id="d5296-106">If passing a URI to affected APIs, modify the string to be a legal path first.</span></span><ul><li><span data-ttu-id="d5296-107">Удалите схему из URL-адресов вручную (например, удалите `file://` из URL-адресов)</span><span class="sxs-lookup"><span data-stu-id="d5296-107">Remove the scheme from URLs manually (e.g. remove `file://` from URLs)</span></span>

- <span data-ttu-id="d5296-108">Передайте универсальный код ресурса (URI) в класс <xref:System.Uri> и используйте <xref:System.Uri.LocalPath></span><span class="sxs-lookup"><span data-stu-id="d5296-108">Pass the URI to the <xref:System.Uri> class and use <xref:System.Uri.LocalPath></span></span>

<span data-ttu-id="d5296-109">Кроме того, вы можете отказаться от новой нормализации путей, установив для переключателя `Switch.System.IO.UseLegacyPathHandling` AppContext значение true.</span><span class="sxs-lookup"><span data-stu-id="d5296-109">Alternatively, you can opt out of the new path normalization by setting the `Switch.System.IO.UseLegacyPathHandling` AppContext switch to true.</span></span>

| <span data-ttu-id="d5296-110">name</span><span class="sxs-lookup"><span data-stu-id="d5296-110">Name</span></span>    | <span data-ttu-id="d5296-111">Значение</span><span class="sxs-lookup"><span data-stu-id="d5296-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d5296-112">Область</span><span class="sxs-lookup"><span data-stu-id="d5296-112">Scope</span></span>   | <span data-ttu-id="d5296-113">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="d5296-113">Edge</span></span>        |
| <span data-ttu-id="d5296-114">Version</span><span class="sxs-lookup"><span data-stu-id="d5296-114">Version</span></span> | <span data-ttu-id="d5296-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="d5296-115">4.6.2</span></span>       |
| <span data-ttu-id="d5296-116">Type</span><span class="sxs-lookup"><span data-stu-id="d5296-116">Type</span></span>    | <span data-ttu-id="d5296-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="d5296-117">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="d5296-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d5296-118">Affected APIs</span></span>

- <xref:System.IO.Path.GetDirectoryName(System.String)?displayProperty=nameWithType>
- <xref:System.IO.Path.GetPathRoot(System.String)?displayProperty=nameWithType>
