---
title: Ограничения асинхронного режима
ms.date: 09/04/2020
description: Описывает ограничения асинхронных API и некоторых альтернатив, которые можно использовать вместо них.
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89515999"
---
# <a name="async-limitations"></a>Ограничения асинхронного режима

SQLite не поддерживает асинхронный ввод-вывод. Асинхронные методы ADO.NET будут выполняться синхронно в Microsoft.Data.Sqlite. Старайтесь не вызывать их.

Вместо этого используйте [общий кэш](connection-strings.md#cache) и [упреждающее протоколирование](https://www.sqlite.org/wal.html) для повышения производительности и параллелизма.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> Упреждающее протоколирование включено по умолчанию для баз данных, созданных с помощью [Entity Framework Core](/ef/core/).
