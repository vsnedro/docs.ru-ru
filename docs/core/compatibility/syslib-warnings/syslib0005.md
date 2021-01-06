---
title: Предупреждение SYSLIB0005
description: Сведения об устаревших элементах, которые приводят к появлению предупреждения во время компиляции SYSLIB0005.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 1263a4d327c735268f77ed56bdcea6a4cbed4bfa
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596367"
---
# <a name="syslib0005-the-global-assembly-cache-gac-is-not-supported"></a>SYSLIB0005. Глобальный кэш сборок не поддерживается

В .NET Core и .NET 5.0 и более поздних версий больше не используется концепция глобального кэша сборок, которая присутствует в .NET Framework. Чтобы помочь разработчикам отказаться от этих API, некоторые связанные с глобальным кэшем сборок API были помечены как устаревшие, начиная с версии .NET 5.0. При использовании этих API во время компиляции создается предупреждение `SYSLIB0005`.

Следующие связанные с глобальным кэшем сборок API помечены как устаревшие:

- <xref:System.Reflection.Assembly.GlobalAssemblyCache?displayProperty=nameWithType>

  Библиотеки и приложения не должны использовать API <xref:System.Reflection.Assembly.GlobalAssemblyCache> для определения поведения во время выполнения, так как в .NET Core и .NET 5 и более поздних версий он всегда возвращает `false`.

## <a name="workarounds"></a>Обходные пути

Если приложение запрашивает свойство <xref:System.Reflection.Assembly.GlobalAssemblyCache>, рассмотрите возможность удалить вызов. Если вы используете значение <xref:System.Reflection.Assembly.GlobalAssemblyCache> для выбора между потоками сборки в глобальном кэше сборок и вне него во время выполнения, еще раз оцените, требуется ли такой поток по-прежнему в приложении .NET 5 и более поздних версий.

[!INCLUDE [suppress-syslib-warning](../../../../includes/suppress-syslib-warning.md)]

## <a name="see-also"></a>См. также

- [Глобальный кэш сборок](../../../framework/app-domains/gac.md)
