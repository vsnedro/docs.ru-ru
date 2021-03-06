---
title: Перенос крупных решений в ASP.NET Core
description: Рассмотрим, как перенести крупные приложения ASP.NET MVC в ASP.NET Core.
author: ardalis
ms.date: 11/13/2020
ms.openlocfilehash: d3ebd71213e074ce80dc83fc3230c4e365275ad3
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401727"
---
# <a name="migrate-large-solutions-to-aspnet-core"></a>Перенос крупных решений в ASP.NET Core

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Для переноса больших решений из платформа .NET Framework в .NET Core требуется определенное планирование. Зависимости должны быть перенесены или обновлены до проектов, зависящих от них. Существуют средства, которые могут определить зависимости и предложить помощь при переходе на .NET Core. В зависимости от приложения, его области действия и текущих шаблонов использования при миграции могут применяться различные стратегии. Переносите ли вы все это одновременно или со временем параллельно с текущей системой? Вы переносите текущую систему в новую, а затем постепенно заменяете ее функциональность?

В этой главе вы узнаете, как создать план миграции для большого решения, как использовать средства для помощи в миграции, а также некоторые стратегии, которые следует учитывать при миграции.

## <a name="references"></a>Ссылки

- [Какие разделы важны для переноса больших приложений MVC и веб-API в .NET Core?](https://twitter.com/ardalis/status/1313669040859217921)
- [Перенос кода в .NET Core из .NET Framework](../../core/porting/index.md)

>[!div class="step-by-step"]
>[Назад](testing-differences.md)
>[Вперед](identify-migration-sequence.md)
