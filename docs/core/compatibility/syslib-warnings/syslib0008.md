---
title: Предупреждение SYSLIB0008
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0008.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2b573f4b28cdf79107395f5cb38a4226d0ccc11e
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596334"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008. CreatePdbGenerator не поддерживается

API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> помечен как устаревший, начиная с версии .NET 5.0. При его использовании во время компиляции создается предупреждение `SYSLIB0008`.

## <a name="suppress-the-warning"></a>Отключение предупреждения

Если вы не можете изменить код, это предупреждение можно отключить с помощью директивы `#pragma` или параметра проекта `<NoWarn>`. Примеры см. в разделе [Отключение предупреждений](../syslib-obsoletions.md#suppress-warnings).
