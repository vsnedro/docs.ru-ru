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
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a>SYSLIB0009. Методы проверки подлинности и предварительной проверки подлинности AuthenticationManager не поддерживаются

Следующие API помечены как устаревшие, начиная с версии .NET 5.0. При использовании этих API во время компиляции создается предупреждение `SYSLIB0009`.

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a>Отключение предупреждения

Если вы не можете изменить код, это предупреждение можно отключить с помощью директивы `#pragma` или параметра проекта `<NoWarn>`. Примеры см. в разделе [Отключение предупреждений](syslib-obsoletions.md#suppress-warnings).
