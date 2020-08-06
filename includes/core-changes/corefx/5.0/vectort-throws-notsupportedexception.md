---
ms.openlocfilehash: 43ebb37124b8efe077b9f81fe5351bd7db2c72f7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302724"
---
### <a name="vectort-always-throws-notsupportedexception-for-unsupported-types"></a><span data-ttu-id="09ecc-101">Vector\<T> всегда вызывает исключение NotSupportedException для неподдерживаемых типов</span><span class="sxs-lookup"><span data-stu-id="09ecc-101">Vector\<T> always throws NotSupportedException for unsupported types</span></span>

<span data-ttu-id="09ecc-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> теперь всегда вызывает <xref:System.NotSupportedException> для неподдерживаемых параметров типа.</span><span class="sxs-lookup"><span data-stu-id="09ecc-102"><xref:System.Numerics.Vector%601?displayProperty=nameWithType> now always throws a <xref:System.NotSupportedException> for unsupported type parameters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="09ecc-103">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="09ecc-103">Change description</span></span>

<span data-ttu-id="09ecc-104">Ранее члены <xref:System.Numerics.Vector%601> не всегда вызывали <xref:System.NotSupportedException>, если у `T` был [неподдерживаемый тип](#unsupported-types).</span><span class="sxs-lookup"><span data-stu-id="09ecc-104">Previously, members of <xref:System.Numerics.Vector%601> would not always throw a <xref:System.NotSupportedException> when `T` was an [unsupported type](#unsupported-types).</span></span> <span data-ttu-id="09ecc-105">Исключение не всегда вызывалось из-за путей к коду, поддерживающих аппаратное ускорение.</span><span class="sxs-lookup"><span data-stu-id="09ecc-105">The exception wasn't always thrown because of code paths that supported hardware acceleration.</span></span> <span data-ttu-id="09ecc-106">Например, для `Vector<bool> + Vector<bool>` возвращалось `default` вместо вызова исключения на платформах без аппаратного ускорения, например ARM32.</span><span class="sxs-lookup"><span data-stu-id="09ecc-106">For example, `Vector<bool> + Vector<bool>` returned `default` instead of throwing an exception on platforms that have no hardware acceleration, such as ARM32.</span></span> <span data-ttu-id="09ecc-107">Для неподдерживаемых типов члены <xref:System.Numerics.Vector%601> демонстрируют несогласованное поведение на разных платформах и с разными конфигурациями оборудования.</span><span class="sxs-lookup"><span data-stu-id="09ecc-107">For unsupported types, <xref:System.Numerics.Vector%601> members exhibited inconsistent behavior across different platforms and hardware configurations.</span></span>

<span data-ttu-id="09ecc-108">Начиная с .NET 5.0, члены <xref:System.Numerics.Vector%601> всегда вызывают <xref:System.NotSupportedException> во всех конфигурациях оборудования, если `T` не является поддерживаемым типом.</span><span class="sxs-lookup"><span data-stu-id="09ecc-108">Starting in .NET 5.0, <xref:System.Numerics.Vector%601> members always throw a <xref:System.NotSupportedException> on all hardware configurations when `T` is not a supported type.</span></span>

##### <a name="unsupported-types"></a><span data-ttu-id="09ecc-109">Неподдерживаемые типы</span><span class="sxs-lookup"><span data-stu-id="09ecc-109">Unsupported types</span></span>

<span data-ttu-id="09ecc-110">Поддерживаемые типы для параметра типа <xref:System.Numerics.Vector%601>:</span><span class="sxs-lookup"><span data-stu-id="09ecc-110">The supported types for the type parameter of <xref:System.Numerics.Vector%601> are:</span></span>

- `byte`
- `sbyte`
- `short`
- `ushort`
- `int`
- `uint`
- `long`
- `ulong`
- `float`
- `double`

<span data-ttu-id="09ecc-111">Поддерживаемые типы не изменились, но могут измениться в будущем.</span><span class="sxs-lookup"><span data-stu-id="09ecc-111">The supported types have not changed, however, they may change in the future.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="09ecc-112">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="09ecc-112">Version introduced</span></span>

<span data-ttu-id="09ecc-113">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="09ecc-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="09ecc-114">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="09ecc-114">Recommended action</span></span>

<span data-ttu-id="09ecc-115">Не используйте неподдерживаемый тип для параметра типа <xref:System.Numerics.Vector%601>.</span><span class="sxs-lookup"><span data-stu-id="09ecc-115">Don't use an unsupported type for the type parameter of <xref:System.Numerics.Vector%601>.</span></span>

#### <a name="category"></a><span data-ttu-id="09ecc-116">Категория</span><span class="sxs-lookup"><span data-stu-id="09ecc-116">Category</span></span>

<span data-ttu-id="09ecc-117">Библиотеки Core .NET</span><span class="sxs-lookup"><span data-stu-id="09ecc-117">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="09ecc-118">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="09ecc-118">Affected APIs</span></span>

- <span data-ttu-id="09ecc-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> и все связанные члены</span><span class="sxs-lookup"><span data-stu-id="09ecc-119"><xref:System.Numerics.Vector%601?displayProperty=fullName> and all its members</span></span>

<!--

#### Affected APIs

- ``T:System.Numerics.Vector`1``

-->
