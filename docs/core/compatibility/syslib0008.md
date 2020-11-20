---
title: Предупреждение SYSLIB0008
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0008.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 22ac5b4c5f57ec3f92585ee8d1f8cf278a15dbb0
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440599"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a>SYSLIB0008. CreatePdbGenerator не поддерживается

API <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> помечен как устаревший, начиная с версии .NET 5.0. При его использовании во время компиляции создается предупреждение `SYSLIB0008`.

## <a name="suppress-the-warning"></a>Отключение предупреждения

Если вы не можете изменить код, это предупреждение можно отключить с помощью директивы `#pragma` или параметра проекта `<NoWarn>`. Примеры см. в разделе [Отключение предупреждений](syslib-obsoletions.md#suppress-warnings).
