---
title: Предупреждение SYSLIB0012
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 9b3fa94029efb2343e6dbbeb3ae36195f0956523
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596333"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012. Assembly.CodeBase и Assembly.EscapedCodeBase устарели

Следующие API помечены как устаревшие, начиная с версии .NET 5.0. При их использовании во время компиляции создается предупреждение `SYSLIB0012`.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a>Обходные пути

Взамен рекомендуется использовать <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]
