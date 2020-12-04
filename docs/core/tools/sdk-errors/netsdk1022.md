---
title: 'NETSDK1022: Duplicate items were included.'
description: Как разрешить сообщение о повторяющемся элементе на основе параметров по умолчанию.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: c2bdbbb5503e5e4f6e6826f95f5a2cb08c908ceb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717878"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: Duplicate items were included.

**Эта статья относится к:** ✔️ пакету SDK для .NET Core 2.1.100 и более поздних версий

Начиная с Visual Studio 2017 или MSBuild версии 15.3 пакет SDK для .NET автоматически включает элементы из каталога проекта по умолчанию.  Сюда входят целевые объекты `Compile` и `Content`.  Это поможет значительно очистить файл проекта и упростить его.

Можно вернуться к предыдущему поведению, задав для свойства значение false.

Пример для элементов `Compile`:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
