---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных SQLite, выполняющиеся в памяти.
ms.openlocfilehash: fbda5787d95a9ce462752b985f847af0b0551fa6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555371"
---
# <a name="in-memory-databases"></a>Базы данных в памяти

Выполняющиеся в памяти базы данных SQLite — это базы данных, которые полностью хранятся в памяти, а не на диске. Для создания выполняющейся в памяти базы данных используется специальное имя файла источника данных `:memory:`. Когда подключение закрывается, база данных удаляется. При использовании `:memory:` каждое подключение создает собственную базу данных.

```connectionstring
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Общий доступ к выполняющимся в памяти базам данных

Выполняющиеся в памяти базы данных могут совместно использоваться несколькими подключениями, если указать `Mode=Memory` и `Cache=Shared` в строке подключения. С помощью ключевого слова `Data Source` можно задать имя для выполняющейся в памяти базы данных. Строки подключения, в которых указано одно и то же имя, будут обращаться к одной и той же выполняющейся в памяти базе данных. База данных существует, пока остается открытым хотя бы одно подключение к ней. На GitHub имеется [пример](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs), который это демонстрирует.

```connectionstring
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
