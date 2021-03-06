---
title: 'NETSDK1013: Значение TargetFramework не распознано.'
description: Как определить и задать допустимое значение TargetFramework
author: marcpop
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1013
ms.openlocfilehash: bcaed878b663f8bc957e8469ffd78caa9babf710
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94445700"
---
# <a name="netsdk1013-the-targetframework-value-was-not-recognized"></a>NETSDK1013: Значение TargetFramework не распознано

**Эта статья относится к:** ✔️ пакету SDK для .NET 3.1.100 и более поздних версий

Пакет SDK пытается выполнить синтаксический анализ значений, предоставленных в файле проекта для `<TargetFramework>` или `<TargetFrameworks>`, в хорошо известное значение.  Если значение не распознано, для `TargetFrameworkIdentifier` или `TargetFrameworkVersion` может быть задана пустая строка или `Unsupported`.

Чтобы устранить эту проблему, проверьте правильность написания значения `TargetFramework` из списка [поддерживаемых платформ](../../../standard/frameworks.md).
Вы также можете задать свойства `TargetFrameworkIdentifier` и `TargetFrameworkVersion` напрямую в файле проекта.

```xml
<PropertyGroup Condition="'$(TargetFrameworkIdentifier)' == ''">
  <TargetFrameworkIdentifier>.NETCOREAPP</TargetFrameworkIdentifier>
  <TargetFrameworkVersion>3.1</TargetFrameworkVersion>
</PropertyGroup>
```
