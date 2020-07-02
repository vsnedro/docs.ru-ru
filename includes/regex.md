---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802859"
---

> [!WARNING]
> <span data-ttu-id="c6ebf-101">При использовании <xref:System.Text.RegularExpressions> для обработки ненадежных входных данных передайте время ожидания.</span><span class="sxs-lookup"><span data-stu-id="c6ebf-101">When using <xref:System.Text.RegularExpressions> to process untrusted input, pass a timeout.</span></span> <span data-ttu-id="c6ebf-102">Злонамеренный пользователь может предоставить входные данные для `RegularExpressions`, что делает возможными [атаки типа "отказ в обслуживании"](https://www.us-cert.gov/ncas/tips/ST04-015).</span><span class="sxs-lookup"><span data-stu-id="c6ebf-102">A malicious user can provide input to `RegularExpressions` causing a [Denial-of-Service attack](https://www.us-cert.gov/ncas/tips/ST04-015).</span></span> <span data-ttu-id="c6ebf-103">API платформы ASP.NET Core, использующие `RegularExpressions`, передают время ожидания.</span><span class="sxs-lookup"><span data-stu-id="c6ebf-103">ASP.NET Core framework APIs that use `RegularExpressions` pass a timeout.</span></span>
