---
title: Различия архитектуры ASP.NET MVC и ASP.NET Core
description: Изучите архитектурные различия между ASP.NET и ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: 96477f2393482380eee9891e9b2dbbb6445e15bd
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401822"
---
# <a name="architectural-differences-between-aspnet-mvc-and-aspnet-core"></a>Различия архитектуры ASP.NET MVC и ASP.NET Core

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Существует множество архитектурных различий между ASP.NET MVC на платформа .NET Framework и ASP.NET Core. Важно иметь общее представление об этих различиях, так как команды оценивают работу, связанную с переносом приложений ASP.NET MVC в ASP.NET Core. В этой главе рассматриваются все способы, в которых ASP.NET Core существенно отличаются от ASP.NET MVC.

## <a name="breaking-changes"></a>Критические изменения

.NET Core — это кросс-платформенная перезапись платформа .NET Framework. [Между двумя платформами существует много критических изменений](../../core/compatibility/fx-core.md). В следующих разделах приведены определенные различия между разработкой и ASP.NET приложений MVC и ASP.NET Core. Также ознакомьтесь с документацией, чтобы определить, какие библиотеки платформы вы используете, которые, возможно, потребуется изменить. Во многих случаях существует заменяющий пакет NuGet для заполнения всех пропусков, оставшихся между платформа .NET Framework и .NET Core. В редких случаях может потребоваться найти стороннее решение или реализовать новый пользовательский код для устранения несовместимости.

>[!div class="step-by-step"]
>[Назад](additional-migration-resources.md)
>[Вперед](app-startup-differences.md)
