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
# <a name="netsdk1079-the-microsoftaspnetcoreall-package-is-not-supported-when-targeting-net-core-30-or-higher"></a>NETSDK1079. Пакет Microsoft.AspNetCore.Al не поддерживается, если он ориентирован на .NET Core 3.0 или более поздней версии.

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 3.1.100 и более поздних версий

Это сообщение об ошибке может появиться в следующих случаях:

- Проект ASP.NET Core переориентирован с .NET Core 2.2 или более ранней версии на .NET Core 3.0 или более поздней версии.
- В проекте используется пакет Microsoft.AspNetCore.All.

Удалите `PackageReference` для Microsoft.AspNetCore.All.  Также может потребоваться добавить ссылки на пакет для тех пакетов, на которые имеются ссылки из Microsoft.AspNetCore.All, но которые не включены в общую платформу ASP.NET Core.  Эти пакеты перечислены здесь: [Переход от Microsoft.AspNetCore.All к Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage#migrating-from-microsoftaspnetcoreall-to-microsoftaspnetcoreapp).

См. также раздел [Миграция с ASP.NET Core 2.2 на 3.0](/aspnet/core/migration/22-to-30).
