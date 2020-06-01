---
title: Source Link и библиотеки .NET
description: Практические рекомендации по использованию Source Link для повышения эффективности отладки для библиотек .NET.
ms.date: 01/15/2019
ms.openlocfilehash: 5dee2a6b1f77daa641351e02c1dd3e0a38f66550
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201978"
---
# <a name="source-link"></a><span data-ttu-id="e8bbd-103">Source Link</span><span class="sxs-lookup"><span data-stu-id="e8bbd-103">Source Link</span></span>

<span data-ttu-id="e8bbd-104">Source Link — это технология, которая дает возможность разработчикам выполнять отладку исходного кода сборок .NET из NuGet.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-104">Source Link is a technology that enables source code debugging of .NET assemblies from NuGet by developers.</span></span> <span data-ttu-id="e8bbd-105">Source Link выполняется при создании пакета NuGet и внедряет метаданные системы управления версиями внутри сборки и пакета.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-105">Source Link executes when creating the NuGet package and embeds source control metadata inside assemblies and the package.</span></span> <span data-ttu-id="e8bbd-106">Разработчики, загрузившие пакет и включившие Source Link в Visual Studio, могут выполнить исходный код по шагам.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-106">Developers who download the package and have Source Link enabled in Visual Studio can step into its source code.</span></span> <span data-ttu-id="e8bbd-107">Source Link предоставляет метаданные системы управления версиями для создания эффективной среды отладки.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-107">Source Link provides source control metadata to create a great debugging experience.</span></span>

## <a name="source-link-demo"></a><span data-ttu-id="e8bbd-108">Демонстрация Source Link</span><span class="sxs-lookup"><span data-stu-id="e8bbd-108">Source Link demo</span></span>

<!--markdownlint-disable MD034 -->
> [!VIDEO https://www.youtube.com/embed/gyRGhCQPkB4?start=61]

## <a name="using-source-link"></a><span data-ttu-id="e8bbd-109">Использование Source Link</span><span class="sxs-lookup"><span data-stu-id="e8bbd-109">Using Source Link</span></span>

<span data-ttu-id="e8bbd-110">Инструкции по использованию Source Link можно найти в репозитории GitHub [dotnet/sourceLink](https://github.com/dotnet/sourcelink/blob/master/README.md).</span><span class="sxs-lookup"><span data-stu-id="e8bbd-110">Instructions for using Source Link can be found on the [dotnet/sourcelink](https://github.com/dotnet/sourcelink/blob/master/README.md) GitHub repository.</span></span>

<span data-ttu-id="e8bbd-111">Вы можете использовать [обозреватель пакетов NuGet](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer), чтобы убедиться, что метаданные Source Link успешно внедрены в пакет.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-111">You can use [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) to confirm that the Source Link metadata has been successfully embedded in the package.</span></span> <span data-ttu-id="e8bbd-112">Проверьте наличие метаданных `Repository` с идентификатором фиксации и убедитесь, что для каждой DLL-библиотеки целевого пакета есть PDB-файлы.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-112">Check the `Repository` metadata is present with a commit identifier and that .pdb files are located with each target's .dll.</span></span>

<span data-ttu-id="e8bbd-113">![Ссылка на источник в обозревателе пакетов NuGet](./media/sourcelink/nuget-package-explorer-sourcelink.png "Ссылка на источник в обозревателе пакетов NuGet")</span><span class="sxs-lookup"><span data-stu-id="e8bbd-113">![Source Link in NuGet Package Explorer](./media/sourcelink/nuget-package-explorer-sourcelink.png "Source Link in NuGet Package Explorer")</span></span>

<span data-ttu-id="e8bbd-114">✔ РЕКОМЕНДУЕТСЯ использовать Source Link для добавления метаданных системы управления версиями в сборки и пакеты NuGet.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-114">✔️ CONSIDER using Source Link to add source control metadata to your assemblies and NuGet packages.</span></span>

> [!TIP]
> <span data-ttu-id="e8bbd-115">Вы можете дополнительно повысить эффективность отладки путем добавления атрибутов отладчика в типы.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-115">You can further enhance a developer's debugging experience by adding debugger attributes to your types.</span></span>
>
> * <span data-ttu-id="e8bbd-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> может определять, как класс или поле будет отображаться в окнах переменных отладчика.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-116"><xref:System.Diagnostics.DebuggerDisplayAttribute> can customize how a class or field is displayed in the debugger variable windows.</span></span>
> * <span data-ttu-id="e8bbd-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> дает отладчику указание о сквозной обработке кода (вместо выполнения по шагам).</span><span class="sxs-lookup"><span data-stu-id="e8bbd-117"><xref:System.Diagnostics.DebuggerStepThroughAttribute> instructs the debugger to step through the code instead of stepping into the code.</span></span>
> * <span data-ttu-id="e8bbd-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> определяет, будет ли член отображаться в окнах переменных отладчика.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-118"><xref:System.Diagnostics.DebuggerBrowsableAttribute> controls whether a member is displayed in the debugger variable windows.</span></span>

<span data-ttu-id="e8bbd-119">✔ РЕКОМЕНДУЕТСЯ публиковать файлы символов (`*.pdb`).</span><span class="sxs-lookup"><span data-stu-id="e8bbd-119">✔️ CONSIDER publishing symbol files (`*.pdb`).</span></span>

> <span data-ttu-id="e8bbd-120">Для повышения качества отладки библиотеки следует публиковать файлы символов, а также использовать ссылки на источник.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-120">For the best debugging experience your library should publish symbol files as well as use Source Link.</span></span> <span data-ttu-id="e8bbd-121">См. дополнительные сведения о [файлах и пакетах символов](./nuget.md#symbol-packages).</span><span class="sxs-lookup"><span data-stu-id="e8bbd-121">For more information about symbol files and symbol packages, see [Symbol packages](./nuget.md#symbol-packages).</span></span>

<span data-ttu-id="e8bbd-122">✔️ РЕКОМЕНДУЕТСЯ включить детерминированные сборки.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-122">✔️ CONSIDER enabling deterministic builds.</span></span>

> <span data-ttu-id="e8bbd-123">Детерминированные сборки позволяют убедиться в том, что полученный двоичный файл построен на основе указанного источника и обеспечивает трассировку.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-123">Deterministic builds enable verification that the resulting binary was built from the specified source and provide traceability.</span></span> <span data-ttu-id="e8bbd-124">См. сведения о [детерминированных сборках](https://github.com/clairernovotny/DeterministicBuilds) и инструкции по их включению.</span><span class="sxs-lookup"><span data-stu-id="e8bbd-124">For more information about deterministic builds and instructions for enabling them, see [Deterministic Builds](https://github.com/clairernovotny/DeterministicBuilds).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e8bbd-125">[Назад](dependencies.md)
>[Вперед](publish-nuget-package.md)</span><span class="sxs-lookup"><span data-stu-id="e8bbd-125">[Previous](dependencies.md)
[Next](publish-nuget-package.md)</span></span>
