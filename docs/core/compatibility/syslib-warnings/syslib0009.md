---
title: Предупреждение SYSLIB0009
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0009.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 922fcc30b2b1577976e4e88e3f7631e19d4b2cce
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596360"
---
# <a name="syslib0009-the-authenticationmanager-authenticate-and-preauthenticate-methods-are-not-supported"></a>SYSLIB0009. Методы проверки подлинности и предварительной проверки подлинности AuthenticationManager не поддерживаются

Следующие API помечены как устаревшие, начиная с версии .NET 5.0. При использовании этих API во время компиляции создается предупреждение `SYSLIB0009`.

- <xref:System.Net.AuthenticationManager.Authenticate%2A?displayProperty=nameWithType>
- <xref:System.Net.AuthenticationManager.PreAuthenticate%2A?displayProperty=nameWithType>

## <a name="suppress-the-warning"></a>Отключение предупреждения

Если вы не можете изменить код, это предупреждение можно отключить с помощью директивы `#pragma` или параметра проекта `<NoWarn>`. Примеры см. в разделе [Отключение предупреждений](../syslib-obsoletions.md#suppress-warnings).
