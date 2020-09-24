---
ms.openlocfilehash: 760c9ce2427bc1f5e9276e66ecb6d2cf2ed83c16
ms.sourcegitcommit: a8730298170b8d96b4272e0c3dfc9819c606947b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90738828"
---
### <a name="parameter-names-changed-in-rc1"></a><span data-ttu-id="089bf-101">В RC1 изменились имена параметров</span><span class="sxs-lookup"><span data-stu-id="089bf-101">Parameter names changed in RC1</span></span>

<span data-ttu-id="089bf-102">Некоторые имена параметров ссылочных сборок изменились для соответствия с именами параметров в сборках реализации.</span><span class="sxs-lookup"><span data-stu-id="089bf-102">Some reference assembly parameter names have changed to match parameter names in the implementation assemblies.</span></span>

#### <a name="change-description"></a><span data-ttu-id="089bf-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="089bf-103">Change description</span></span>

<span data-ttu-id="089bf-104">В предыдущей предварительной версии и версии RC .NET 5.0 некоторые имена параметров [ссылочных сборок](../../../../docs/standard/assembly/reference-assemblies.md) отличаются от соответствующих им параметров в сборке реализации.</span><span class="sxs-lookup"><span data-stu-id="089bf-104">In previous .NET 5.0 preview and RC versions, some [reference assembly](../../../../docs/standard/assembly/reference-assemblies.md) parameter names are different to their corresponding parameters in the implementation assembly.</span></span> <span data-ttu-id="089bf-105">Это может вызвать проблемы при использовании именованных аргументов и отражения.</span><span class="sxs-lookup"><span data-stu-id="089bf-105">This can cause problems while using named arguments and reflection.</span></span>

<span data-ttu-id="089bf-106">В .NET 5.0 RC2 несоответствующие имена параметров были изменены в ссылочных сборках, чтобы точно соответствовать именам параметров в сборках реализации.</span><span class="sxs-lookup"><span data-stu-id="089bf-106">In .NET 5.0 RC2, these mismatched parameter names were updated in the reference assemblies to exactly match the corresponding parameter names in the implementation assemblies.</span></span>

<span data-ttu-id="089bf-107">В следующей таблице приведены измененные API-интерфейсы и имена параметров.</span><span class="sxs-lookup"><span data-stu-id="089bf-107">The following table shows the APIs and parameter names that changed.</span></span>

| <span data-ttu-id="089bf-108">API</span><span class="sxs-lookup"><span data-stu-id="089bf-108">API</span></span> | <span data-ttu-id="089bf-109">Старое имя параметра</span><span class="sxs-lookup"><span data-stu-id="089bf-109">Old parameter name</span></span> | <span data-ttu-id="089bf-110">Новое имя параметра</span><span class="sxs-lookup"><span data-stu-id="089bf-110">New parameter name</span></span> |
| - | - | - |
| <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)> | `traceOptions` | `traceFlags` |
| <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=nameWithType> | `suffix` | `prefix` |

#### <a name="reason-for-change"></a><span data-ttu-id="089bf-111">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="089bf-111">Reason for change</span></span>

<span data-ttu-id="089bf-112">Имена параметров были изменены для согласованности и предотвращения сбоев при использовании именованных аргументов и отражения.</span><span class="sxs-lookup"><span data-stu-id="089bf-112">The parameter names were changed for consistency and to avoid failures when using named arguments and reflection.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="089bf-113">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="089bf-113">Version introduced</span></span>

<span data-ttu-id="089bf-114">5.0 RC2</span><span class="sxs-lookup"><span data-stu-id="089bf-114">5.0 RC2</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="089bf-115">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="089bf-115">Recommended action</span></span>

<span data-ttu-id="089bf-116">Если возникла ошибка компилятора из-за изменения имени параметра, измените имя параметра соответствующим образом.</span><span class="sxs-lookup"><span data-stu-id="089bf-116">If you encounter a compiler error due to a parameter name change, update the parameter name accordingly.</span></span>

#### <a name="category"></a><span data-ttu-id="089bf-117">Категория</span><span class="sxs-lookup"><span data-stu-id="089bf-117">Category</span></span>

<span data-ttu-id="089bf-118">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="089bf-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="089bf-119">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="089bf-119">Affected APIs</span></span>

- <xref:System.Diagnostics.ActivityContext.%23ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)>
- <xref:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.ActivityContext.#ctor(System.Diagnostics.ActivityTraceId,System.Diagnostics.ActivitySpanId,System.Diagnostics.ActivityTraceFlags,System.String,System.Boolean)`
- `M:System.Globalization.CompareInfo.IsPrefix(System.ReadOnlySpan{System.Char},System.ReadOnlySpan{System.Char},System.Globalization.CompareOptions,System.Int32@)`

-->
