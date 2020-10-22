---
title: Критические изменения MSBuild
description: В этой статье приведен список критических изменений в MSBuild для .NET Core.
ms.date: 02/10/2020
ms.openlocfilehash: 9b0fba30c8955a6099bde0dc95b4df65a151d9e6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159496"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="a7904-103">Критические изменения MSBuild</span><span class="sxs-lookup"><span data-stu-id="a7904-103">MSBuild breaking changes</span></span>

<span data-ttu-id="a7904-104">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="a7904-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="a7904-105">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="a7904-105">Breaking change</span></span> | <span data-ttu-id="a7904-106">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="a7904-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="a7904-107">Значение TargetFramework изменено с netcoreapp на net</span><span class="sxs-lookup"><span data-stu-id="a7904-107">TargetFramework change from netcoreapp to net</span></span>](#targetframework-change-from-netcoreapp-to-net) | <span data-ttu-id="a7904-108">5.0</span><span class="sxs-lookup"><span data-stu-id="a7904-108">5.0</span></span> |
| [<span data-ttu-id="a7904-109">Символ препроцессора NETCOREAPP3_1 не определен при ориентации на .NET 5</span><span class="sxs-lookup"><span data-stu-id="a7904-109">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="a7904-110">5.0</span><span class="sxs-lookup"><span data-stu-id="a7904-110">5.0</span></span> |
| [<span data-ttu-id="a7904-111">Изменение поведения PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="a7904-111">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="a7904-112">5.0</span><span class="sxs-lookup"><span data-stu-id="a7904-112">5.0</span></span> |
| [<span data-ttu-id="a7904-113">Файлы Directory.Packages.props импортируются по умолчанию</span><span class="sxs-lookup"><span data-stu-id="a7904-113">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="a7904-114">5.0</span><span class="sxs-lookup"><span data-stu-id="a7904-114">5.0</span></span> |
| [<span data-ttu-id="a7904-115">Изменение имен файлов манифеста ресурса</span><span class="sxs-lookup"><span data-stu-id="a7904-115">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="a7904-116">3.0</span><span class="sxs-lookup"><span data-stu-id="a7904-116">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="a7904-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a7904-117">.NET 5.0</span></span>

[!INCLUDE [targetframework-name-change](../../../includes/core-changes/msbuild/5.0/targetframework-name-change.md)]

***

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="a7904-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a7904-118">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
