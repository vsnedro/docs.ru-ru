---
title: NETSDK1079. Пакет Microsoft.AspNetCore.Al не поддерживается, если он ориентирован на .NET Core 3.0 или более поздней версии.
description: Как разрешить переход с Microsoft.AspNetCore.App
author: dsplaisted
ms.topic: error-reference
ms.date: 10/09/2020
f1_keywords:
- NETSDK1079
ms.openlocfilehash: e0b7aba909dbd2931f755238a2de2418d294751d
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445706"
---
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a><span data-ttu-id="40fa1-103">NETSDK1079. Пакет Microsoft.AspNetCore.Al не поддерживается, если он ориентирован на .NET Core 3.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="40fa1-103">NETSDK1079: The Microsoft.AspNetCore.All package is not supported when targeting .NET Core 3.0 or higher.</span></span>

<span data-ttu-id="40fa1-104">**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.100 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="40fa1-104">**This article applies to:** ✔️ .NET Core SDK 3.1.100 and later versions</span></span>

<span data-ttu-id="40fa1-105">Это сообщение об ошибке может появиться в следующих случаях:</span><span class="sxs-lookup"><span data-stu-id="40fa1-105">You may receive this error message when:</span></span>

- <span data-ttu-id="40fa1-106">Проект ASP.NET Core переориентирован с .NET Core 2.2 или более ранней версии на .NET Core 3.0 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="40fa1-106">You retarget an ASP.NET Core project from .NET Core 2.2 or earlier to .NET Core 3.0 or later.</span></span>
- <span data-ttu-id="40fa1-107">В проекте используется пакет Microsoft.AspNetCore.All.</span><span class="sxs-lookup"><span data-stu-id="40fa1-107">The project uses the Microsoft.AspNetCore.All package.</span></span>

<span data-ttu-id="40fa1-108">Удалите `PackageReference` для Microsoft.AspNetCore.All.</span><span class="sxs-lookup"><span data-stu-id="40fa1-108">Remove the `PackageReference` for Microsoft.AspNetCore.All.</span></span>  <span data-ttu-id="40fa1-109">Также может потребоваться добавить ссылки на пакет для тех пакетов, на которые имеются ссылки из Microsoft.AspNetCore.All, но которые не включены в общую платформу ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="40fa1-109">You may also need to add package references for packages that were referenced from Microsoft.AspNetCore.All but are not included in the ASP.NET Core shared framework.</span></span>  <span data-ttu-id="40fa1-110">Эти пакеты перечислены здесь: [Переход от Microsoft.AspNetCore.All к Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span><span class="sxs-lookup"><span data-stu-id="40fa1-110">These packages are listed here: [Migrating from Microsoft.AspNetCore.All to Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).</span></span>

<span data-ttu-id="40fa1-111">См. также раздел [Миграция с ASP.NET Core 2.2 на 3.0](/aspnet/core/migration/22-to-30).</span><span class="sxs-lookup"><span data-stu-id="40fa1-111">See also [Migrate from ASP.NET Core 2.2 to 3.0](/aspnet/core/migration/22-to-30)</span></span>
