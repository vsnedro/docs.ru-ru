---
title: Критические изменения в WPF
description: Список критических изменений в Windows Presentation Framework для .NET Core и .NET 5.
ms.date: 09/08/2020
ms.openlocfilehash: 3bd5cb585509118fbc3ca9ca08c6ed15b4853b93
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679309"
---
# <a name="breaking-changes-in-windows-presentation-framework-wpf"></a><span data-ttu-id="69419-103">Критические изменения в Windows Presentation Framework (WPF)</span><span class="sxs-lookup"><span data-stu-id="69419-103">Breaking changes in Windows Presentation Framework (WPF)</span></span>

<span data-ttu-id="69419-104">Поддержка WPF была добавлена в .NET Core в версии 3.0.</span><span class="sxs-lookup"><span data-stu-id="69419-104">WPF support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="69419-105">В этой статье перечислены критические изменения для WPF, сгруппированные по версии .NET, в которой они появились.</span><span class="sxs-lookup"><span data-stu-id="69419-105">This article lists breaking changes for WPF by the .NET version in which they were introduced.</span></span> <span data-ttu-id="69419-106">Если вы обновляете приложение WPF с .NET Framework или с предыдущей версии .NET Core (3.0 или более поздней), эта статья для вас актуальна.</span><span class="sxs-lookup"><span data-stu-id="69419-106">If you're upgrading a WPF app from .NET Framework or from a previous version of .NET Core (3.0 or later), this article applies to you.</span></span>

<span data-ttu-id="69419-107">На этой странице описаны следующие критические изменения:</span><span class="sxs-lookup"><span data-stu-id="69419-107">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="69419-108">Критическое изменение</span><span class="sxs-lookup"><span data-stu-id="69419-108">Breaking change</span></span> | <span data-ttu-id="69419-109">Представленная версия</span><span class="sxs-lookup"><span data-stu-id="69419-109">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="69419-110">Свойству OutputType задано значение WinExe для приложений WPF и WinForms</span><span class="sxs-lookup"><span data-stu-id="69419-110">OutputType set to WinExe for WPF and WinForms apps</span></span>](#outputtype-set-to-winexe-for-wpf-and-winforms-apps) | <span data-ttu-id="69419-111">5.0</span><span class="sxs-lookup"><span data-stu-id="69419-111">5.0</span></span> |
| [<span data-ttu-id="69419-112">В приложениях WinForms и WPF используется Microsoft.NET.Sdk</span><span class="sxs-lookup"><span data-stu-id="69419-112">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>](#winforms-and-wpf-apps-use-microsoftnetsdk) | <span data-ttu-id="69419-113">5.0</span><span class="sxs-lookup"><span data-stu-id="69419-113">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="69419-114">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="69419-114">.NET 5.0</span></span>

[!INCLUDE [automatically-infer-winexe-output-type](../../../includes/core-changes/windowsforms/5.0/automatically-infer-winexe-output-type.md)]

***

[!INCLUDE [sdk-and-target-framework-change](../../../includes/core-changes/windowsforms/5.0/sdk-and-target-framework-change.md)]

***
