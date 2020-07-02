---
ms.openlocfilehash: 29c66edfeb1690199aac39b9c3076d161b2075d4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621439"
---
### <a name="contractinvariant-or-contractrequirestexception-do-not-consider-stringisnullorempty-to-be-pure"></a><span data-ttu-id="42cc6-101">Contract.Invariant или Contract.Requires\<TException> не учитывает необходимость чистоты String.IsNullOrEmpty</span><span class="sxs-lookup"><span data-stu-id="42cc6-101">Contract.Invariant or Contract.Requires\<TException> do not consider String.IsNullOrEmpty to be pure</span></span>

#### <a name="details"></a><span data-ttu-id="42cc6-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="42cc6-102">Details</span></span>

<span data-ttu-id="42cc6-103">В приложениях, предназначенных для .NET Framework 4.6.1, если контракт инвариантности для <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> или контракт предусловия для <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> вызывает метод <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType>, средство перезаписи выдает предупреждение компилятора CC1036: &quot;обнаружен вызов метода "System.String.IsNullOrWhteSpace(System.String)" без [Pure] в методе.&quot; Это предупреждение, а не ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="42cc6-103">For apps that target the .NET Framework 4.6.1, if the invariant contract for <xref:System.Diagnostics.Contracts.Contract.Invariant%2A?displayProperty=nameWithType> or the precondition contract for <xref:System.Diagnostics.Contracts.Contract.Requires%2A?displayProperty=nameWithType)> calls the <xref:System.String.IsNullOrEmpty%2A?displayProperty=nameWithType> method, the rewriter emits compiler warning CC1036: &quot;Detected call to method 'System.String.IsNullOrWhteSpace(System.String)' without [Pure] in method.&quot; This is a compiler warning rather than a compiler error.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="42cc6-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="42cc6-104">Suggestion</span></span>

<span data-ttu-id="42cc6-105">Проблема была устранена в [билете 339 на сайте GitHub](https://github.com/Microsoft/CodeContracts/issues/339).</span><span class="sxs-lookup"><span data-stu-id="42cc6-105">This behavior was addressed in [GitHub Issue #339](https://github.com/Microsoft/CodeContracts/issues/339).</span></span> <span data-ttu-id="42cc6-106">Чтобы устранить это предупреждение, можно скачать и скомпилировать обновленную версию исходного кода для инструментов контрактов кода с сайта [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="42cc6-106">To eliminate this warning, you can download and compile an updated version of the source code for the Code Contracts tool from [GitHub](https://github.com/Microsoft/CodeContracts/blob/master/README.md).</span></span> <span data-ttu-id="42cc6-107">Сведения о скачивании находятся в нижней части страницы.</span><span class="sxs-lookup"><span data-stu-id="42cc6-107">Download information is found at the bottom of the page.</span></span>

| <span data-ttu-id="42cc6-108">name</span><span class="sxs-lookup"><span data-stu-id="42cc6-108">Name</span></span>    | <span data-ttu-id="42cc6-109">Значение</span><span class="sxs-lookup"><span data-stu-id="42cc6-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="42cc6-110">Область</span><span class="sxs-lookup"><span data-stu-id="42cc6-110">Scope</span></span>   |<span data-ttu-id="42cc6-111">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="42cc6-111">Minor</span></span>|
|<span data-ttu-id="42cc6-112">Version</span><span class="sxs-lookup"><span data-stu-id="42cc6-112">Version</span></span>|<span data-ttu-id="42cc6-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="42cc6-113">4.6.1</span></span>|
|<span data-ttu-id="42cc6-114">Type</span><span class="sxs-lookup"><span data-stu-id="42cc6-114">Type</span></span>|<span data-ttu-id="42cc6-115">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="42cc6-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="42cc6-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="42cc6-116">Affected APIs</span></span>

-<xref:System.Diagnostics.Contracts.Contract.Invariant(System.Boolean)?displayProperty=nameWithType></li><li><xref:System.Diagnostics.Contracts.Contract.Requires(System.Boolean)?displayProperty=nameWithType></li></ul>|
