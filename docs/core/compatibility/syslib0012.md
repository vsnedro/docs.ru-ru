---
title: Предупреждение SYSLIB0012
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2ed93b6eefbaa861faca319f0cc9bf19ac741f3b
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333106"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a><span data-ttu-id="a64ee-103">SYSLIB0012. Assembly.CodeBase и Assembly.EscapedCodeBase устарели</span><span class="sxs-lookup"><span data-stu-id="a64ee-103">SYSLIB0012: Assembly.CodeBase and Assembly.EscapedCodeBase are obsolete</span></span>

<span data-ttu-id="a64ee-104">Следующие API помечены как устаревшие, начиная с версии .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="a64ee-104">The following APIs are marked as obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="a64ee-105">При их использовании во время компиляции создается предупреждение `SYSLIB0012`.</span><span class="sxs-lookup"><span data-stu-id="a64ee-105">Using them in code generates warning `SYSLIB0012` at compile time.</span></span>

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

<span data-ttu-id="a64ee-106">Обходной путь</span><span class="sxs-lookup"><span data-stu-id="a64ee-106">Workaround</span></span>

<span data-ttu-id="a64ee-107">Взамен рекомендуется использовать <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a64ee-107">Use <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType> instead.</span></span>
