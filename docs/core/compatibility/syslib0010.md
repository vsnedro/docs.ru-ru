---
title: Предупреждение SYSLIB0010
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0010.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dcd331aa5c68381ea29848bc54ee4b1a5e75330d
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333110"
---
# <a name="syslib0010-unsupported-remoting-apis"></a><span data-ttu-id="fa551-103">SYSLIB0010. Неподдерживаемые API удаленного взаимодействия</span><span class="sxs-lookup"><span data-stu-id="fa551-103">SYSLIB0010: Unsupported remoting APIs</span></span>

<span data-ttu-id="fa551-104">Технология [удаленного взаимодействия .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) является устаревшей, и соответствующая инфраструктура существует только в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa551-104">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71)) is a legacy technology, and the infrastructure exists only in .NET Framework.</span></span> <span data-ttu-id="fa551-105">Следующие API, связанные с удаленным взаимодействием, помечены как устаревшие, начиная с версии .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="fa551-105">The following remoting-related APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="fa551-106">При их использовании во время компиляции создается предупреждение `SYSLIB0010`.</span><span class="sxs-lookup"><span data-stu-id="fa551-106">Using them in code generates warning `SYSLIB0010` at compile time.</span></span>

- <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType>

## <a name="workaround"></a><span data-ttu-id="fa551-107">Обходной путь</span><span class="sxs-lookup"><span data-stu-id="fa551-107">Workaround</span></span>

<span data-ttu-id="fa551-108">Для взаимодействия с объектами в других приложениях или на других компьютерах рекомендуется использовать WCF или службы RESTFUL на основе HTTP.</span><span class="sxs-lookup"><span data-stu-id="fa551-108">Consider using WCF or HTTP-based REST services to communicate with objects in other applications or across machines.</span></span> <span data-ttu-id="fa551-109">Дополнительные сведения см. в разделе [Технологии .NET Framework, недоступные в .NET Core](../porting/net-framework-tech-unavailable.md).</span><span class="sxs-lookup"><span data-stu-id="fa551-109">For more information, see [.NET Framework technologies unavailable on .NET Core](../porting/net-framework-tech-unavailable.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fa551-110">См. также</span><span class="sxs-lookup"><span data-stu-id="fa551-110">See also</span></span>

- <span data-ttu-id="fa551-111">[Удаленное взаимодействие .NET](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span><span class="sxs-lookup"><span data-stu-id="fa551-111">[.NET remoting](/previous-versions/dotnet/netframework-1.1/kwdt6w2k(v=vs.71))</span></span>
