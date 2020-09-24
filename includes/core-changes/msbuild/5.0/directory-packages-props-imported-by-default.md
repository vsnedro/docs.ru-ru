---
ms.openlocfilehash: 4a916a4178535763712ebd58fde1a81e456da0d1
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538827"
---
### <a name="directorypackagesprops-files-is-imported-by-default"></a><span data-ttu-id="c4cec-101">Файлы Directory.Packages.props импортируются по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c4cec-101">Directory.Packages.props files is imported by default</span></span>

<span data-ttu-id="c4cec-102">Файлы *.props* NuGet автоматически импортируют файл с именем *Directory.Packages.props*, если он находится в папке проекта или любом из ее предков.</span><span class="sxs-lookup"><span data-stu-id="c4cec-102">NuGet's *.props* files automatically import a file named *Directory.Packages.props* if it's found in the project folder or any of its ancestors.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c4cec-103">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="c4cec-103">Version introduced</span></span>

<span data-ttu-id="c4cec-104">5.0, предварительная версия 8</span><span class="sxs-lookup"><span data-stu-id="c4cec-104">5.0 Preview 8</span></span>

#### <a name="change-description"></a><span data-ttu-id="c4cec-105">Описание изменений</span><span class="sxs-lookup"><span data-stu-id="c4cec-105">Change description</span></span>

<span data-ttu-id="c4cec-106">В предыдущих версиях .NET в файле проекта у вас мог быть файл с именем *Directory.Packages.props*, который автоматически не импортировался файлом *.props* NuGet во время сборки.</span><span class="sxs-lookup"><span data-stu-id="c4cec-106">In previous .NET versions, you could have a file named *Directory.Packages.props* in your project file and it wouldn't be automatically imported by NuGet's *.props* file at build time.</span></span>

<span data-ttu-id="c4cec-107">Начиная с .NET 5.0 такой файл автоматически *импортируется*, если он существует в папке проекта или любом из ее предков.</span><span class="sxs-lookup"><span data-stu-id="c4cec-107">Starting in .NET 5.0, such a file *is* automatically imported if it exists in the project folder or any of its ancestors.</span></span> <span data-ttu-id="c4cec-108">Если в папке проекта есть файл с таким именем, эта операция автоматического импорта может изменить поведение сборки.</span><span class="sxs-lookup"><span data-stu-id="c4cec-108">If you have a file with this name in your project folder, this automatic import could change behavior of the build.</span></span> <span data-ttu-id="c4cec-109">Например, файл будет импортирован, но не импортировался ранее, или порядок, в котором он импортируется, может измениться в случае его намеренного импорта.</span><span class="sxs-lookup"><span data-stu-id="c4cec-109">For example, the file will be imported but it wasn't before, or the order of when it's imported could change if you specifically import it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c4cec-110">Причина изменения</span><span class="sxs-lookup"><span data-stu-id="c4cec-110">Reason for change</span></span>

<span data-ttu-id="c4cec-111">Это изменение было внесено для поддержки [централизованного управления версиями пакетов](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) для NuGet.</span><span class="sxs-lookup"><span data-stu-id="c4cec-111">This change was made in order to support [central package versioning](https://github.com/NuGet/Home/wiki/Centrally-managing-NuGet-package-versions) for NuGet.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c4cec-112">Рекомендованное действие</span><span class="sxs-lookup"><span data-stu-id="c4cec-112">Recommended action</span></span>

<span data-ttu-id="c4cec-113">Переименуйте существующий файл *Directory.Packages.props*, если он не должен импортироваться автоматически.</span><span class="sxs-lookup"><span data-stu-id="c4cec-113">Rename the existing *Directory.Packages.props* file if it should not be imported automatically.</span></span>

#### <a name="category"></a><span data-ttu-id="c4cec-114">Категория</span><span class="sxs-lookup"><span data-stu-id="c4cec-114">Category</span></span>

<span data-ttu-id="c4cec-115">MSBuild</span><span class="sxs-lookup"><span data-stu-id="c4cec-115">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c4cec-116">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c4cec-116">Affected APIs</span></span>

<span data-ttu-id="c4cec-117">Н/Д</span><span class="sxs-lookup"><span data-stu-id="c4cec-117">N/A</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
