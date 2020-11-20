---
title: 'NETSDK1022: Duplicate items were included.'
description: Как разрешить сообщение о повторяющемся элементе на основе параметров по умолчанию.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: bc803f5316bf09c12c563f1a63b8385d1be4e9ce
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506640"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: Duplicate items were included.

**Эта статья относится к:** ✔️ пакету SDK для .NET 2.1.100 и более поздних версий

Начиная с Visual Studio 2017 или MSBuild версии 15.3 пакет SDK для .NET автоматически включает элементы из каталога проекта по умолчанию.  Сюда входят целевые объекты `Compile` и `Content`.  Это поможет значительно очистить файл проекта и упростить его.

Можно вернуться к предыдущему поведению, задав для свойства значение false.

Пример для элементов `Compile`:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
