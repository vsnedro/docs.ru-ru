---
ms.openlocfilehash: b893966ceb65246ed6a7d214011b17ca14c50d5a
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85802859"
---

> [!WARNING]
> При использовании <xref:System.Text.RegularExpressions> для обработки ненадежных входных данных передайте время ожидания. Злонамеренный пользователь может предоставить входные данные для `RegularExpressions`, что делает возможными [атаки типа "отказ в обслуживании"](https://www.us-cert.gov/ncas/tips/ST04-015). API платформы ASP.NET Core, использующие `RegularExpressions`, передают время ожидания.
