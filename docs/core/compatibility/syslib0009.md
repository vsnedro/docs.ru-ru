---
title: Предупреждение SYSLIB0009
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0009.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 47b4f595a54800370da90f61d838c665df8b6091
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439980"
---
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a><span data-ttu-id="f4819-103">SYSLIB0009. Методы проверки подлинности и предварительной проверки подлинности AuthenticationManager не поддерживаются</span><span class="sxs-lookup"><span data-stu-id="f4819-103">SYSLIB0009: The AuthenticationManager Authenticate and PreAuthenticate methods are not supported</span></span>

<span data-ttu-id="f4819-104">Следующие API помечены как устаревшие, начиная с версии .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="f4819-104">The following APIs are marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="f4819-105">При использовании этих API во время компиляции создается предупреждение `SYSLIB0009`.</span><span class="sxs-lookup"><span data-stu-id="f4819-105">Use of these APIs generates warning `SYSLIB0009` at compile time.</span></span>

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a><span data-ttu-id="f4819-106">Отключение предупреждения</span><span class="sxs-lookup"><span data-stu-id="f4819-106">Suppress the warning</span></span>

<span data-ttu-id="f4819-107">Если вы не можете изменить код, это предупреждение можно отключить с помощью директивы `#pragma` или параметра проекта `<NoWarn>`.</span><span class="sxs-lookup"><span data-stu-id="f4819-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="f4819-108">Примеры см. в разделе [Отключение предупреждений](syslib-obsoletions.md#suppress-warnings).</span><span class="sxs-lookup"><span data-stu-id="f4819-108">For examples, see [Suppress warnings](syslib-obsoletions.md#suppress-warnings).</span></span>
