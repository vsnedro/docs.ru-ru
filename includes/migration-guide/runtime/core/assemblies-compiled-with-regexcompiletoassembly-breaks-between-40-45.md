---
ms.openlocfilehash: 424872b25436c7fcbe603639028e813eed6f9b99
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496649"
---
### <a name="assemblies-compiled-with-regexcompiletoassembly-breaks-between-40-and-45"></a><span data-ttu-id="b3f6e-101">Сборки, скомпилированные с прерываниями Regex.CompileToAssembly между версиями 4.0 и 4.5</span><span class="sxs-lookup"><span data-stu-id="b3f6e-101">Assemblies compiled with Regex.CompileToAssembly breaks between 4.0 and 4.5</span></span>

#### <a name="details"></a><span data-ttu-id="b3f6e-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="b3f6e-102">Details</span></span>

<span data-ttu-id="b3f6e-103">Если сборка компилированных регулярных выражений создается с помощью .NET Framework 4.5, но предназначена для .NET Framework 4, попытка использовать одно из регулярных выражений в этой сборке в системе с .NET Framework 4 создает исключение.</span><span class="sxs-lookup"><span data-stu-id="b3f6e-103">If an assembly of compiled regular expressions is built with the .NET Framework 4.5 but targets the .NET Framework 4, attempting to use one of the regular expressions in that assembly on a system with .NET Framework 4 installed throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b3f6e-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="b3f6e-104">Suggestion</span></span>

<span data-ttu-id="b3f6e-105">Чтобы обойти эту проблему, можно воспользоваться одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="b3f6e-105">To work around this problem, you can do either of the following:</span></span><ul><li><span data-ttu-id="b3f6e-106">создать сборку, содержащую регулярные выражения, с помощью .NET Framework 4;</span><span class="sxs-lookup"><span data-stu-id="b3f6e-106">Build the assembly that contains the regular expressions with the .NET Framework 4.</span></span></li><li><span data-ttu-id="b3f6e-107">использовать интерпретированное регулярное выражение.</span><span class="sxs-lookup"><span data-stu-id="b3f6e-107">Use an interpreted regular expression.</span></span></li></ul>

| <span data-ttu-id="b3f6e-108">name</span><span class="sxs-lookup"><span data-stu-id="b3f6e-108">Name</span></span>    | <span data-ttu-id="b3f6e-109">Значение</span><span class="sxs-lookup"><span data-stu-id="b3f6e-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b3f6e-110">Область</span><span class="sxs-lookup"><span data-stu-id="b3f6e-110">Scope</span></span>   |<span data-ttu-id="b3f6e-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="b3f6e-111">Minor</span></span>|
|<span data-ttu-id="b3f6e-112">Version</span><span class="sxs-lookup"><span data-stu-id="b3f6e-112">Version</span></span>|<span data-ttu-id="b3f6e-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b3f6e-113">4.5</span></span>|
|<span data-ttu-id="b3f6e-114">Type</span><span class="sxs-lookup"><span data-stu-id="b3f6e-114">Type</span></span>|<span data-ttu-id="b3f6e-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="b3f6e-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="b3f6e-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="b3f6e-116">Affected APIs</span></span>

- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])?displayProperty=nameWithType>
- <xref:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName)`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[])`
- `M:System.Text.RegularExpressions.Regex.CompileToAssembly(System.Text.RegularExpressions.RegexCompilationInfo[],System.Reflection.AssemblyName,System.Reflection.Emit.CustomAttributeBuilder[],System.String)`

-->
