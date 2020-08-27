---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720210"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="86a81-101">Распознавание URI UNC-путей в UNIX</span><span class="sxs-lookup"><span data-stu-id="86a81-101">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="86a81-102">Класс <xref:System.Uri> теперь распознает строки, начинающиеся с двух косых черт (`//`) как пути в формате UNC в операционных системах UNIX.</span><span class="sxs-lookup"><span data-stu-id="86a81-102">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="86a81-103">Это изменение делает поведение для таких строк согласованным на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="86a81-103">This change makes the behavior for such strings consistent across all platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="86a81-104">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="86a81-104">Change description</span></span>

<span data-ttu-id="86a81-105">В предыдущих версиях .NET класс <xref:System.Uri> распознавал строки, начинающиеся с двух косых черт, например `//contoso`, как абсолютные пути к файлам в операционных системах UNIX.</span><span class="sxs-lookup"><span data-stu-id="86a81-105">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="86a81-106">Однако в Windows такие строки распознаются как UNC-пути.</span><span class="sxs-lookup"><span data-stu-id="86a81-106">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="86a81-107">Начиная с .NET 5.0 класс <xref:System.Uri> распознает строки, начинающиеся с двух косых черт, как UNC-пути на всех платформах, включая UNIX.</span><span class="sxs-lookup"><span data-stu-id="86a81-107">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="86a81-108">Кроме того, свойства ведут себя в соответствии с семантикой UNC:</span><span class="sxs-lookup"><span data-stu-id="86a81-108">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="86a81-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> возвращает `true`.</span><span class="sxs-lookup"><span data-stu-id="86a81-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="86a81-110">Символы обратной косой черты в пути заменяются прямой косой чертой.</span><span class="sxs-lookup"><span data-stu-id="86a81-110">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="86a81-111">Например, `//first\second` преобразуется в `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="86a81-111">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="86a81-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> не кодирует символы процентами.</span><span class="sxs-lookup"><span data-stu-id="86a81-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="86a81-113">Например, `//first/\uFFF0` *не* преобразуется в `//first/%EF%BF%B0`.</span><span class="sxs-lookup"><span data-stu-id="86a81-113">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="86a81-114">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="86a81-114">Version introduced</span></span>

<span data-ttu-id="86a81-115">5.0</span><span class="sxs-lookup"><span data-stu-id="86a81-115">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="86a81-116">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="86a81-116">Recommended action</span></span>

<span data-ttu-id="86a81-117">От разработчика не требуется никаких действий.</span><span class="sxs-lookup"><span data-stu-id="86a81-117">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="86a81-118">Категория</span><span class="sxs-lookup"><span data-stu-id="86a81-118">Category</span></span>

<span data-ttu-id="86a81-119">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="86a81-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="86a81-120">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="86a81-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
