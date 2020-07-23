---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281315"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="62055-101">Изменение в поведении для Vector2.Lerp и Vector4.Lerp</span><span class="sxs-lookup"><span data-stu-id="62055-101">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="62055-102">Изменена реализация <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> и <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType>, чтобы корректно учитывать ошибку округления чисел с плавающей запятой.</span><span class="sxs-lookup"><span data-stu-id="62055-102">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

#### <a name="change-description"></a><span data-ttu-id="62055-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="62055-103">Change description</span></span>

<span data-ttu-id="62055-104">Ранее <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> и <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> были реализованы как `value1 + (value2 - value1) * amount`.</span><span class="sxs-lookup"><span data-stu-id="62055-104">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="62055-105">Тем не менее, из-за ошибки округления чисел с плавающей запятой этот алгоритм не всегда возвращает `value2`, когда `amount` равно `1.0f`.</span><span class="sxs-lookup"><span data-stu-id="62055-105">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="62055-106">В .NET 5.0 и более поздних версий в реализации используется тот же алгоритм, что и в <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, то есть `(value1 * (1.0f - amount)) + (value2 * amount)`.</span><span class="sxs-lookup"><span data-stu-id="62055-106">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="62055-107">В этом алгоритме корректно учитывается ошибка округления.</span><span class="sxs-lookup"><span data-stu-id="62055-107">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="62055-108">Таким образом, теперь, если `amount` равно `1.0f`, результат будет точно равен `value2`.</span><span class="sxs-lookup"><span data-stu-id="62055-108">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="62055-109">Обновленный алгоритм также может быть свободно оптимизирован с использованием <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> (если доступно).</span><span class="sxs-lookup"><span data-stu-id="62055-109">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="62055-110">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="62055-110">Version introduced</span></span>

<span data-ttu-id="62055-111">5.0 (предварительная версия 7)</span><span class="sxs-lookup"><span data-stu-id="62055-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="62055-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="62055-112">Recommended action</span></span>

<span data-ttu-id="62055-113">Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="62055-113">No action is necessary.</span></span> <span data-ttu-id="62055-114">Если вы хотите сохранить старое поведение, можно реализовать собственную функцию `Lerp`, которая использует предыдущий алгоритм `value1 + (value2 - value1) * amount`.</span><span class="sxs-lookup"><span data-stu-id="62055-114">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

#### <a name="category"></a><span data-ttu-id="62055-115">Категория</span><span class="sxs-lookup"><span data-stu-id="62055-115">Category</span></span>

<span data-ttu-id="62055-116">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="62055-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="62055-117">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="62055-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
