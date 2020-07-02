---
ms.openlocfilehash: 0bd90b3d479a7e0897aaf78b7718ae156a4a239f
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620195"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="d04cc-101">Сборки, скомпилированные с прерываниями Regex.CompileToAssembly между версиями 4.0 и 4.5</span><span class="sxs-lookup"><span data-stu-id="d04cc-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="d04cc-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="d04cc-102">Details</span></span>

<span data-ttu-id="d04cc-103">Если сборка компилированных регулярных выражений создается с помощью .NET Framework 4.5, но предназначена для .NET Framework 4, попытка использовать одно из регулярных выражений в этой сборке в системе с .NET Framework 4 создает исключение.</span><span class="sxs-lookup"><span data-stu-id="d04cc-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="d04cc-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="d04cc-104">Suggestion</span></span>

<span data-ttu-id="d04cc-105">Чтобы обойти эту проблему, можно воспользоваться одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="d04cc-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="d04cc-106">создать сборку, содержащую регулярные выражения, с помощью .NET Framework 4;</span><span class="sxs-lookup"><span data-stu-id="d04cc-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="d04cc-107">использовать интерпретированное регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="d04cc-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="d04cc-108">name</span><span class="sxs-lookup"><span data-stu-id="d04cc-108">Name</span></span>    | <span data-ttu-id="d04cc-109">Значение</span><span class="sxs-lookup"><span data-stu-id="d04cc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="d04cc-110">Область</span><span class="sxs-lookup"><span data-stu-id="d04cc-110">Scope</span></span>   |<span data-ttu-id="d04cc-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="d04cc-111">Minor</span></span>|
|<span data-ttu-id="d04cc-112">Version</span><span class="sxs-lookup"><span data-stu-id="d04cc-112">Version</span></span>|<span data-ttu-id="d04cc-113">4.5</span><span class="sxs-lookup"><span data-stu-id="d04cc-113">4.5</span></span>|
|<span data-ttu-id="d04cc-114">Type</span><span class="sxs-lookup"><span data-stu-id="d04cc-114">Type</span></span>|<span data-ttu-id="d04cc-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="d04cc-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d04cc-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="d04cc-116">Affected APIs</span></span>

-<xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType></li><li><xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType></li></ul>|
