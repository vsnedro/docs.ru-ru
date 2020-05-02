---
title: Базы данных в памяти
ms.date: 12/13/2019
description: Узнайте, как использовать базы данных SQLite, выполняющиеся в памяти.
ms.openlocfilehash: 408c81f538e27dcfffad20db74b7809912b7905f
ms.sourcegitcommit: a9b8945630426a575ab0a332e568edc807666d1b
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2020
ms.locfileid: "80391212"
---
# <a name="in-memory-databases"></a>Базы данных в памяти

Выполняющиеся в памяти базы данных SQLite — это базы данных, которые полностью хранятся в памяти, а не на диске. Для создания выполняющейся в памяти базы данных используется специальное имя файла источника данных `:memory:`. Когда подключение закрывается, база данных удаляется. При использовании `:memory:` каждое подключение создает собственную базу данных.

```ConnectionString
Data Source=:memory:
```

## <a name="shareable-in-memory-databases"></a>Общий доступ к выполняющимся в памяти базам данных

Выполняющиеся в памяти базы данных могут совместно использоваться несколькими подключениями, если указать `Mode=Memory` и `Cache=Shared` в строке подключения. С помощью ключевого слова `Data Source` можно задать имя для выполняющейся в памяти базы данных. Строки подключения, в которых указано одно и то же имя, будут обращаться к одной и той же выполняющейся в памяти базе данных. База данных существует, пока остается открытым хотя бы одно подключение к ней. На GitHub имеется [пример](https://github.com/dotnet/docs/blob/master/samples/snippets/standard/data/sqlite/InMemorySample/Program.cs), который это демонстрирует.

```ConnectionString
Data Source=InMemorySample;Mode=Memory;Cache=Shared
```
