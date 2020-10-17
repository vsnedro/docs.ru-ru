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
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a><span data-ttu-id="acec9-103">NETSDK1145: отсутствует целевой объект или пакет APPHOST</span><span class="sxs-lookup"><span data-stu-id="acec9-103">NETSDK1145: Targeting or apphost pack missing</span></span>

<span data-ttu-id="acec9-104">**Эта статья относится к:** ✔️ пакету SDK для .NET 5.0.100 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="acec9-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="acec9-105">Когда пакет SDK для .NET выдает ошибку NETSDK1145, это означает, что целевой пакет или пакет APPHOST не установлен, а восстановление пакетов NuGet не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="acec9-105">When the .NET SDK issues error NETSDK1145, the targeting or apphost pack is not installed and NuGet package restore is not supported.</span></span> <span data-ttu-id="acec9-106">Обычно это происходит из-за наличия более нового пакета SDK, отличного от того, который входит в состав проектов Visual Studio для C++/CLI.</span><span class="sxs-lookup"><span data-stu-id="acec9-106">This is typically caused by having a newer SDK than the one included in Visual Studio for C++/CLI projects.</span></span> <span data-ttu-id="acec9-107">Обновите Visual Studio, удалите файл _global.json_, если он задает определенную версию пакета SDK, и удалите новый пакет SDK.</span><span class="sxs-lookup"><span data-stu-id="acec9-107">Upgrade Visual Studio, remove _global.json_ if it specifies a certain SDK version, and uninstall the newer SDK.</span></span> <span data-ttu-id="acec9-108">Кроме того, можно переопределить целевой объект или версию APPHOST.</span><span class="sxs-lookup"><span data-stu-id="acec9-108">Alternatively, you could override the targeting or apphost version.</span></span> <span data-ttu-id="acec9-109">Найдите версию, которая находится в каталоге Pack из сообщения об ошибке и сопоставляет ее с целевой платформой проекта.</span><span class="sxs-lookup"><span data-stu-id="acec9-109">Find the version that exists under the pack directory from the error message and matches the target framework of the project.</span></span> <span data-ttu-id="acec9-110">Добавьте в проект следующий код:</span><span class="sxs-lookup"><span data-stu-id="acec9-110">Add the following to the project:</span></span>

<span data-ttu-id="acec9-111">Для пакета APPHOST</span><span class="sxs-lookup"><span data-stu-id="acec9-111">For apphost pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

<span data-ttu-id="acec9-112">Для целевого пакета</span><span class="sxs-lookup"><span data-stu-id="acec9-112">For targeting pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
