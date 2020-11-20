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
# <a name="netsdk1022-duplicate-items-were-included"></a><span data-ttu-id="dd23c-103">NETSDK1022: Duplicate items were included.</span><span class="sxs-lookup"><span data-stu-id="dd23c-103">NETSDK1022: Duplicate items were included.</span></span>

<span data-ttu-id="dd23c-104">**Эта статья относится к:** ✔️ пакету SDK для .NET 2.1.100 и более поздних версий</span><span class="sxs-lookup"><span data-stu-id="dd23c-104">**This article applies to:** ✔️ .NET 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="dd23c-105">Начиная с Visual Studio 2017 или MSBuild версии 15.3 пакет SDK для .NET автоматически включает элементы из каталога проекта по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="dd23c-105">Starting in Visual Studio 2017 / MSBuild version 15.3, the .NET SDK automatically includes items from the project directory by default.</span></span>  <span data-ttu-id="dd23c-106">Сюда входят целевые объекты `Compile` и `Content`.</span><span class="sxs-lookup"><span data-stu-id="dd23c-106">This includes `Compile` and `Content` targets.</span></span>  <span data-ttu-id="dd23c-107">Это поможет значительно очистить файл проекта и упростить его.</span><span class="sxs-lookup"><span data-stu-id="dd23c-107">This should greatly clean up your project file and reduce the complexity you have there.</span></span>

<span data-ttu-id="dd23c-108">Можно вернуться к предыдущему поведению, задав для свойства значение false.</span><span class="sxs-lookup"><span data-stu-id="dd23c-108">You can revert to the earlier behavior by setting the correct property to false.</span></span>

<span data-ttu-id="dd23c-109">Пример для элементов `Compile`:</span><span class="sxs-lookup"><span data-stu-id="dd23c-109">Example for `Compile` items:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
