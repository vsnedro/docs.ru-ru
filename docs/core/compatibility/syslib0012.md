---
title: Предупреждение SYSLIB0012
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: dc139d5c5cb6d6a34d161147b350b3324d15117e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440586"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012. Assembly.CodeBase и Assembly.EscapedCodeBase устарели

Следующие API помечены как устаревшие, начиная с версии .NET 5.0. При их использовании во время компиляции создается предупреждение `SYSLIB0012`.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

## <a name="workarounds"></a>Обходные пути

Взамен рекомендуется использовать <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.

[!INCLUDE [suppress-syslib-warning](../../../includes/suppress-syslib-warning.md)]
