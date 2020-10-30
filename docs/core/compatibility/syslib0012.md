---
title: Предупреждение SYSLIB0012
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0012.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2ed93b6eefbaa861faca319f0cc9bf19ac741f3b
ms.sourcegitcommit: dfcbc096ad7908cd58a5f0aeabd2256f05266bac
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "92333106"
---
# <a name="syslib0012-assemblycodebase-and-assemblyescapedcodebase-are-obsolete"></a>SYSLIB0012. Assembly.CodeBase и Assembly.EscapedCodeBase устарели

Следующие API помечены как устаревшие, начиная с версии .NET 5.0. При их использовании во время компиляции создается предупреждение `SYSLIB0012`.

- <xref:System.Reflection.Assembly.CodeBase?displayProperty=nameWithType>
- <xref:System.Reflection.Assembly.EscapedCodeBase?displayProperty=nameWithType>

Обходной путь

Взамен рекомендуется использовать <xref:System.Reflection.Assembly.Location?displayProperty=nameWithType>.
