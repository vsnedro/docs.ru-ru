---
ms.openlocfilehash: c090e99cd0569a843a4c505ad11b8da5740213e8
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440483"
---
### <a name="blazor-updated-validation-logic-for-static-web-assets"></a><span data-ttu-id="c916e-101">Blazor: Обновленная логика проверки для статических веб-ресурсов</span><span class="sxs-lookup"><span data-stu-id="c916e-101">Blazor: Updated validation logic for static web assets</span></span>

<span data-ttu-id="c916e-102">При проверке конфликтов для статических веб-ресурсов в ASP.NET Core 3.1 и Blazor WebAssembly 3.2 возникала ошибка.</span><span class="sxs-lookup"><span data-stu-id="c916e-102">There was an issue in conflict validation for static web assets in ASP.NET Core 3.1 and Blazor WebAssembly 3.2.</span></span> <span data-ttu-id="c916e-103">Эта ошибка:</span><span class="sxs-lookup"><span data-stu-id="c916e-103">The issue:</span></span>

* <span data-ttu-id="c916e-104">Не позволяла правильно обнаружить конфликты между ресурсами узла и ресурсами из библиотеки классов Razor (RCL) и приложениями Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="c916e-104">Prevented proper conflict detection between the host assets and assets from Razor Class Libraries (RCLs) and Blazor WebAssembly apps.</span></span>
* <span data-ttu-id="c916e-105">В основном влияет на приложения Blazor WebAssembly, поскольку статические веб-ресурсы в RCL обрабатываются по префиксу `_content/$(PackageId)`.</span><span class="sxs-lookup"><span data-stu-id="c916e-105">Mostly affects Blazor WebAssembly apps, since by default, static web assets in RCLs are served under the `_content/$(PackageId)` prefix.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c916e-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c916e-106">Version introduced</span></span>

<span data-ttu-id="c916e-107">5.0</span><span class="sxs-lookup"><span data-stu-id="c916e-107">5.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="c916e-108">Старое поведение</span><span class="sxs-lookup"><span data-stu-id="c916e-108">Old behavior</span></span>

<span data-ttu-id="c916e-109">Во время разработки статические веб-ресурсы RCL могут быть автоматически переопределены с помощью ресурсов основного проекта по одному и тому же пути к узлу.</span><span class="sxs-lookup"><span data-stu-id="c916e-109">During development, an RCL's static web assets could be silently overridden with host project assets on the same host path.</span></span> <span data-ttu-id="c916e-110">Рассмотрим RCL, который определил статический веб-ресурс для обслуживания по адресу */folder/file.txt*.</span><span class="sxs-lookup"><span data-stu-id="c916e-110">Consider an RCL that has defined a static web asset to be served at */folder/file.txt*.</span></span> <span data-ttu-id="c916e-111">Если узел поместил файл в папку *wwwroot/Folder/File. txt*, то файл на сервере автоматически был переопределен в RCL или приложении Blazor WebAssembly.</span><span class="sxs-lookup"><span data-stu-id="c916e-111">If the host placed a file at *wwwroot/folder/file.txt*, the file on the server silently overrode the file on the RCL or Blazor WebAssembly app.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="c916e-112">Новое поведение</span><span class="sxs-lookup"><span data-stu-id="c916e-112">New behavior</span></span>

<span data-ttu-id="c916e-113">ASP.NET Core правильно определяет, когда возникает эта проблема.</span><span class="sxs-lookup"><span data-stu-id="c916e-113">ASP.NET Core correctly detects when this issue happens.</span></span> <span data-ttu-id="c916e-114">Он информирует пользователя о конфликте, чтобы вы могли предпринять соответствующие действия.</span><span class="sxs-lookup"><span data-stu-id="c916e-114">It informs you, the user, of the conflict so that you can take the appropriate action.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c916e-115">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="c916e-115">Reason for change</span></span>

<span data-ttu-id="c916e-116">Статические веб-ресурсы не предназначены для переопределения файлами на узле *wwwroot* проекта.</span><span class="sxs-lookup"><span data-stu-id="c916e-116">Static web assets weren't intended to be overridable by files on the *wwwroot* host of the project.</span></span> <span data-ttu-id="c916e-117">Если разрешить переопределение этих файлов, могут возникать ошибки, которые трудно диагностировать.</span><span class="sxs-lookup"><span data-stu-id="c916e-117">Allowing for the overriding of those files could lead to errors that are difficult to diagnose.</span></span> <span data-ttu-id="c916e-118">В результате могут возникнуть неопределенные изменения поведения в опубликованных приложениях.</span><span class="sxs-lookup"><span data-stu-id="c916e-118">The result could be undefined behavior changes in published apps.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c916e-119">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="c916e-119">Recommended action</span></span>

<span data-ttu-id="c916e-120">По умолчанию причины для возникновения конфликтов файла RCL с файлом на узле отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="c916e-120">By default, there's no reason for an RCL file to conflict with a file on the host.</span></span> <span data-ttu-id="c916e-121">Файлы RCL имеют префикс `_content/${PackageId}`.</span><span class="sxs-lookup"><span data-stu-id="c916e-121">RCL files are prefixed with `_content/${PackageId}`.</span></span> <span data-ttu-id="c916e-122">Файлы Blazor WebAssembly размещаются в корне пространства URL-адресов узла, что исключает конфликты.</span><span class="sxs-lookup"><span data-stu-id="c916e-122">Blazor WebAssembly files are placed at the root of the host URL space, which makes conflicts easier.</span></span> <span data-ttu-id="c916e-123">Например, приложения Blazor WebAssembly содержат файл *favicon.ico*, который узел может также включить в папку *wwwroot*.</span><span class="sxs-lookup"><span data-stu-id="c916e-123">For example, Blazor WebAssembly apps contain a *favicon.ico* file that the host might also include in its *wwwroot* folder.</span></span>

<span data-ttu-id="c916e-124">Если источником конфликта является файл RCL, это часто означает, что код копирует ресурсы из библиотеки в папку *wwwroot* проекта.</span><span class="sxs-lookup"><span data-stu-id="c916e-124">If the conflict's source is an RCL file, it often means code is copying assets from the library into the project's *wwwroot* folder.</span></span> <span data-ttu-id="c916e-125">Написание кода для копирования файлов позволяет достичь основной цели статических веб-ресурсов.</span><span class="sxs-lookup"><span data-stu-id="c916e-125">Writing code to copy files defeats a primary goal of static web assets.</span></span> <span data-ttu-id="c916e-126">Эта цель заключается в получении обновлений в браузере при обновлении содержимого без активации новой компиляции.</span><span class="sxs-lookup"><span data-stu-id="c916e-126">This goal is fundamental to get updates on the browser when the contents are updated without having to trigger a new compilation.</span></span>

<span data-ttu-id="c916e-127">Вы можете сохранить это поведение и хранить файл на узле.</span><span class="sxs-lookup"><span data-stu-id="c916e-127">You may choose to preserve this behavior and maintain the file on the host.</span></span> <span data-ttu-id="c916e-128">Для этого удалите файл из списка статических веб-ресурсов с настраиваемым целевым объектом MSBuild.</span><span class="sxs-lookup"><span data-stu-id="c916e-128">To do so, remove the file from the list of static web assets with a custom MSBuild target.</span></span>

<span data-ttu-id="c916e-129">Чтобы использовать файл RCL или файл Blazor WebAssembly вместо файла основного проекта, удалите файл из основного проекта.</span><span class="sxs-lookup"><span data-stu-id="c916e-129">To use the RCL's file or the Blazor WebAssembly app's file instead of the host project's file, remove the file from the host project.</span></span>

#### <a name="category"></a><span data-ttu-id="c916e-130">Категория</span><span class="sxs-lookup"><span data-stu-id="c916e-130">Category</span></span>

<span data-ttu-id="c916e-131">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="c916e-131">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c916e-132">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c916e-132">Affected APIs</span></span>

<span data-ttu-id="c916e-133">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="c916e-133">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
