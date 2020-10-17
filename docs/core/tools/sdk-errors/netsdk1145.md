---
title: 'NETSDK1145: отсутствует целевой объект или пакет APPHOST'
description: Устранение проблемы, связанной с отсутствием целевого пакета, в то время как восстановление пакета NuGet не поддерживается
author: wli3
ms.topic: error-reference
ms.date: 09/14/2020
f1_keywords:
- NETSDK1145
ms.openlocfilehash: c343952582cafb63eae388fd216769e6c67d4741
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805312"
---
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a>NETSDK1145: отсутствует целевой объект или пакет APPHOST

**Эта статья относится к:** ✔️ пакету SDK для .NET 5.0.100 и более поздних версий

Когда пакет SDK для .NET выдает ошибку NETSDK1145, это означает, что целевой пакет или пакет APPHOST не установлен, а восстановление пакетов NuGet не поддерживается. Обычно это происходит из-за наличия более нового пакета SDK, отличного от того, который входит в состав проектов Visual Studio для C++/CLI. Обновите Visual Studio, удалите файл _global.json_, если он задает определенную версию пакета SDK, и удалите новый пакет SDK. Кроме того, можно переопределить целевой объект или версию APPHOST. Найдите версию, которая находится в каталоге Pack из сообщения об ошибке и сопоставляет ее с целевой платформой проекта. Добавьте в проект следующий код:

Для пакета APPHOST

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

Для целевого пакета

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
