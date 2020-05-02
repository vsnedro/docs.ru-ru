---
title: Ограничения Xamarin
ms.date: 12/13/2019
description: Описание некоторых из ограничений, которые будут возникать при использовании Xamarin.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450408"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="3d85a-103">Ограничения Xamarin</span><span class="sxs-lookup"><span data-stu-id="3d85a-103">Xamarin limitations</span></span>

<span data-ttu-id="3d85a-104">Microsoft.Data.Sqlite предназначен для .NET Standard 2.0 и поддерживается в Xamarin.</span><span class="sxs-lookup"><span data-stu-id="3d85a-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="3d85a-105">В следующей таблице показано, для каких платформах пакет SQLitePCLRaw по умолчанию предоставляет собственные двоичные файлы SQLite.</span><span class="sxs-lookup"><span data-stu-id="3d85a-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="3d85a-106">Дополнительные сведения об использовании разных пакетов и предоставлении собственных двоичных файлов SQLite см. в разделе [Пользовательские версии SQLite](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="3d85a-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="3d85a-107">Платформа</span><span class="sxs-lookup"><span data-stu-id="3d85a-107">Platform</span></span> | <span data-ttu-id="3d85a-108">Двоичные файлы SQLite</span><span class="sxs-lookup"><span data-stu-id="3d85a-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="3d85a-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="3d85a-109">**Xamarin.Android**</span></span> | <span data-ttu-id="3d85a-110">—</span><span class="sxs-lookup"><span data-stu-id="3d85a-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="3d85a-111">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="3d85a-112">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="3d85a-113">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="3d85a-114">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-114">✔</span></span> |
| <span data-ttu-id="3d85a-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="3d85a-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="3d85a-116">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-116">✔</span></span> |
| <span data-ttu-id="3d85a-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="3d85a-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="3d85a-118">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-118">✔</span></span> |
| <span data-ttu-id="3d85a-119">**Xamarin.TVOS**</span><span class="sxs-lookup"><span data-stu-id="3d85a-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="3d85a-120">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-120">✔</span></span> |
| <span data-ttu-id="3d85a-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="3d85a-121">**UWP**</span></span> | <span data-ttu-id="3d85a-122">—</span><span class="sxs-lookup"><span data-stu-id="3d85a-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="3d85a-123">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="3d85a-124">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="3d85a-125">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="3d85a-126">✔</span><span class="sxs-lookup"><span data-stu-id="3d85a-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="3d85a-127">iOS</span><span class="sxs-lookup"><span data-stu-id="3d85a-127">iOS</span></span>

<span data-ttu-id="3d85a-128">Microsoft.Data.Sqlite пытается автоматически инициализировать пакеты SQLitePCLRaw.</span><span class="sxs-lookup"><span data-stu-id="3d85a-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="3d85a-129">Увы, из-за ограничений статической компиляции для Xamarin.iOS попытка завершается неудачей и появляется следующая ошибка.</span><span class="sxs-lookup"><span data-stu-id="3d85a-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="3d85a-130">Необходимо вызвать `SQLitePCL.raw.SetProvider()`.</span><span class="sxs-lookup"><span data-stu-id="3d85a-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="3d85a-131">Если используется пакет набора, это делается путем вызова `SQLitePCL.Batteries.Init()`.</span><span class="sxs-lookup"><span data-stu-id="3d85a-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="3d85a-132">Чтобы инициализировать пакет, добавьте следующую строку кода в приложение перед использованием Microsoft.Data.Sqlite.</span><span class="sxs-lookup"><span data-stu-id="3d85a-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="3d85a-133">См. также</span><span class="sxs-lookup"><span data-stu-id="3d85a-133">See also</span></span>

* [<span data-ttu-id="3d85a-134">Ограничения асинхронного режима</span><span class="sxs-lookup"><span data-stu-id="3d85a-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="3d85a-135">Пользовательские версии SQLite</span><span class="sxs-lookup"><span data-stu-id="3d85a-135">Custom SQLite versions</span></span>](custom-versions.md)
