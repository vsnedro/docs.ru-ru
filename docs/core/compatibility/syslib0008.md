---
title: Предупреждение SYSLIB0008
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0008.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440599"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a><span data-ttu-id="7ef91-103">SYSLIB0008. CreatePdbGenerator не поддерживается</span><span class="sxs-lookup"><span data-stu-id="7ef91-103">SYSLIB0008: CreatePdbGenerator is not supported</span></span>

<span data-ttu-id="7ef91-104">API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> помечен как устаревший, начиная с версии .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="7ef91-104">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API is marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="7ef91-105">При его использовании во время компиляции создается предупреждение `SYSLIB0008`.</span><span class="sxs-lookup"><span data-stu-id="7ef91-105">Using this API generates warning `SYSLIB0008` at compile time.</span></span>

## <a name="suppress-the-warning"></a><span data-ttu-id="7ef91-106">Отключение предупреждения</span><span class="sxs-lookup"><span data-stu-id="7ef91-106">Suppress the warning</span></span>

<span data-ttu-id="7ef91-107">Если вы не можете изменить код, это предупреждение можно отключить с помощью директивы `#pragma` или параметра проекта `<NoWarn>`.</span><span class="sxs-lookup"><span data-stu-id="7ef91-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="7ef91-108">Примеры см. в разделе [Отключение предупреждений](syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="7ef91-108">For examples, see [Suppress warnings](syslib-obsoletions.md#suppress-warnings).</span></span>
