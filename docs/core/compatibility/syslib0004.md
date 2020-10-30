---
title: Предупреждение SYSLIB0004
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0004.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: ba7cd8a890a89000b241d286c9d8069ba1398849
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333132"
---
# <a name="syslib0004-the-constrained-execution-region-cer-feature-is-not-supported"></a><span data-ttu-id="c8c4d-103">SYSLIB0004. Функция области ограниченного выполнения (CER) не поддерживается</span><span class="sxs-lookup"><span data-stu-id="c8c4d-103">SYSLIB0004: The constrained execution region (CER) feature is not supported</span></span>

<span data-ttu-id="c8c4d-104">Функция [областей ограниченного выполнения (CER)](../../framework/performance/constrained-execution-regions.md) поддерживается только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c8c4d-104">The [Constrained execution regions (CER)](../../framework/performance/constrained-execution-regions.md) feature is supported only in .NET Framework.</span></span> <span data-ttu-id="c8c4d-105">Таким образом, различные связанные этой функцией API помечаются как устаревшие, начиная с версии .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="c8c4d-105">As such, various CER-related APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="c8c4d-106">При использовании этих API во время компиляции создается предупреждение `SYSLIB0004`.</span><span class="sxs-lookup"><span data-stu-id="c8c4d-106">Using these APIs generates warning `SYSLIB0004` at compile time.</span></span>

<span data-ttu-id="c8c4d-107">Следующие интерфейсы API, связанные с функцией областей ограниченного выполнения (CER), являются устаревшими:</span><span class="sxs-lookup"><span data-stu-id="c8c4d-107">The following CER-related APIs are obsolete:</span></span>

- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ExecuteCodeWithGuaranteedCleanup(System.Runtime.CompilerServices.RuntimeHelpers.TryCode,System.Runtime.CompilerServices.RuntimeHelpers.CleanupCode,System.Object)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegions?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareConstrainedRegionsNoOP?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareContractedDelegate(System.Delegate)?displayProperty=nameWithType>
- <xref:System.Runtime.CompilerServices.RuntimeHelpers.ProbeForSufficientStack?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Cer?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.Consistency?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.PrePrepareMethodAttribute?displayProperty=nameWithType>
- <xref:System.Runtime.ConstrainedExecution.ReliabilityContractAttribute?displayProperty=nameWithType>

## <a name="see-also"></a><span data-ttu-id="c8c4d-108">См. также</span><span class="sxs-lookup"><span data-stu-id="c8c4d-108">See also</span></span>

- [<span data-ttu-id="c8c4d-109">Области ограниченного выполнения</span><span class="sxs-lookup"><span data-stu-id="c8c4d-109">Constrained execution regions</span></span>](../../framework/performance/constrained-execution-regions.md)
