---
ms.openlocfilehash: 9c3c0bf7fbd8d45eba84eaa8634fd2d834195702
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617277"
---
### <a name="systemuri-parsing-adheres-to-rfc-3987"></a><span data-ttu-id="4cc22-101">Синтаксический анализ System.Uri соответствует стандарту RFC 3987</span><span class="sxs-lookup"><span data-stu-id="4cc22-101">System.Uri parsing adheres to RFC 3987</span></span>

#### <a name="details"></a><span data-ttu-id="4cc22-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4cc22-102">Details</span></span>

<span data-ttu-id="4cc22-103">Синтаксический анализ URI претерпел ряд изменений в .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="4cc22-103">URI parsing has changed in several ways in .NET Framework 4.5.</span></span> <span data-ttu-id="4cc22-104">Обратите внимание, что эти изменения касаются только кода, предназначенного для .NET Framework 4.5.</span><span class="sxs-lookup"><span data-stu-id="4cc22-104">Note, however, that these changes only affect code targeting .NET Framework 4.5.</span></span> <span data-ttu-id="4cc22-105">Если двоичный файл предназначен для .NET Framework 4.0, будет действовать старое поведение.</span><span class="sxs-lookup"><span data-stu-id="4cc22-105">If a binary targets .NET Framework 4.0, the old behavior will be observed.</span></span> <span data-ttu-id="4cc22-106">В синтаксический анализ URI в .NET Framework 4.5 внесены следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="4cc22-106">Changes to URI parsing in .NET Framework 4.5 include:</span></span>

- <span data-ttu-id="4cc22-107">Синтаксический анализ URI будет выполнять проверку нормализации и символов в соответствии с последними правилами IRI стандарта RFC 3987.</span><span class="sxs-lookup"><span data-stu-id="4cc22-107">URI parsing will perform normalization and character checking according to the latest IRI rules in RFC 3987.</span></span>
- <span data-ttu-id="4cc22-108">Форма нормализации Юникода C будет выполняться только в части узла URI.</span><span class="sxs-lookup"><span data-stu-id="4cc22-108">Unicode normalization form C will only be performed on the host portion of the URI.</span></span>
- <span data-ttu-id="4cc22-109">Недопустимые URI mailto: теперь будут вызывать исключение.</span><span class="sxs-lookup"><span data-stu-id="4cc22-109">Invalid mailto: URIs will now cause an exception.</span></span>
- <span data-ttu-id="4cc22-110">Конечные точки в конце сегмента пути теперь сохраняются.</span><span class="sxs-lookup"><span data-stu-id="4cc22-110">Trailing dots at the end of a path segment are now preserved.</span></span>
- <span data-ttu-id="4cc22-111">Идентификаторы URI `file://` не экранируют символ `?`.</span><span class="sxs-lookup"><span data-stu-id="4cc22-111">`file://` URIs do not escape the `?` character.</span></span>
- <span data-ttu-id="4cc22-112">Управляющие символы Юникода с `U+0080` по `U+009F` не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4cc22-112">Unicode control characters `U+0080` through `U+009F` are not supported.</span></span>
- <span data-ttu-id="4cc22-113">Символы запятой `,` или `%2c` не отменяются автоматически.</span><span class="sxs-lookup"><span data-stu-id="4cc22-113">Comma characters `,` or `%2c` are not automatically unescaped.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4cc22-114">Предложение</span><span class="sxs-lookup"><span data-stu-id="4cc22-114">Suggestion</span></span>

<span data-ttu-id="4cc22-115">Если необходимы старые семантики синтаксического анализа URI в .NET Framework 4.0 (часто они не требуются), их можно использовать, нацелив приложение на .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="4cc22-115">If the old .NET Framework 4.0 URI parsing semantics are necessary (they often aren't), they can be used by targeting .NET Framework 4.0.</span></span> <span data-ttu-id="4cc22-116">Это можно сделать с помощью <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> в сборке или в пользовательском интерфейсе системы проектов Visual Studio на странице свойств проекта.</span><span class="sxs-lookup"><span data-stu-id="4cc22-116">This can be accomplished by using a <xref:System.Runtime.Versioning.TargetFrameworkAttribute?displayProperty=fullName> on the assembly, or through Visual Studio's project system UI in the 'project properties' page.</span></span>

| <span data-ttu-id="4cc22-117">name</span><span class="sxs-lookup"><span data-stu-id="4cc22-117">Name</span></span>    | <span data-ttu-id="4cc22-118">Значение</span><span class="sxs-lookup"><span data-stu-id="4cc22-118">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4cc22-119">Область</span><span class="sxs-lookup"><span data-stu-id="4cc22-119">Scope</span></span>   | <span data-ttu-id="4cc22-120">Значительно</span><span class="sxs-lookup"><span data-stu-id="4cc22-120">Major</span></span>       |
| <span data-ttu-id="4cc22-121">Version</span><span class="sxs-lookup"><span data-stu-id="4cc22-121">Version</span></span> | <span data-ttu-id="4cc22-122">4.5</span><span class="sxs-lookup"><span data-stu-id="4cc22-122">4.5</span></span>         |
| <span data-ttu-id="4cc22-123">Type</span><span class="sxs-lookup"><span data-stu-id="4cc22-123">Type</span></span>    | <span data-ttu-id="4cc22-124">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="4cc22-124">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4cc22-125">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="4cc22-125">Affected APIs</span></span>

- <xref:System.Uri.%23ctor(System.String)>
- <xref:System.Uri.%23ctor(System.String,System.Boolean)>
- <xref:System.Uri.%23ctor(System.String,System.UriKind)>
- <xref:System.Uri.%23ctor(System.Uri,System.String)>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
