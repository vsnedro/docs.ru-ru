---
title: Расположение сборки
description: Расположение сборки .NET определяет, как среда CLR находит ее, а также может ли она использоваться совместно с другими сборками.
ms.date: 08/20/2019
helpviewer_keywords:
- locating assemblies
- assemblies [.NET], location
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
ms.openlocfilehash: 1fa1c486c0cddce4ddcfae7f2df27e2e85c88e66
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687607"
---
# <a name="assembly-location"></a><span data-ttu-id="a91c2-103">Расположение сборки</span><span class="sxs-lookup"><span data-stu-id="a91c2-103">Assembly location</span></span>

<span data-ttu-id="a91c2-104">От места расположения сборки зависит, сможет ли среда CLR найти сборку по ссылке на нее. Это расположение также определяет возможность совместного использования сборки вместе с другими сборками.</span><span class="sxs-lookup"><span data-stu-id="a91c2-104">An assembly's location determines whether the common language runtime can locate it when referenced, and can also determine whether the assembly can be shared with other assemblies.</span></span> <span data-ttu-id="a91c2-105">Для развертывания сборки можно использовать следующие расположения.</span><span class="sxs-lookup"><span data-stu-id="a91c2-105">You can deploy an assembly in the following locations:</span></span>

- <span data-ttu-id="a91c2-106">Каталог приложения или его подкаталоги</span><span class="sxs-lookup"><span data-stu-id="a91c2-106">The application's directory or subdirectories.</span></span>

     <span data-ttu-id="a91c2-107">Это наиболее часто используемое место развертывания сборок.</span><span class="sxs-lookup"><span data-stu-id="a91c2-107">This is the most common location for deploying an assembly.</span></span> <span data-ttu-id="a91c2-108">Структура подкаталогов корневого каталога приложения может зависеть от языка или региональных параметров.</span><span class="sxs-lookup"><span data-stu-id="a91c2-108">The subdirectories of an application's root directory can be based on language or culture.</span></span> <span data-ttu-id="a91c2-109">Если в атрибутах сборки также задан язык и региональные параметры, то она должна располагаться в подкаталоге каталога приложения, название которого соответствует этому языку и региональным параметрам.</span><span class="sxs-lookup"><span data-stu-id="a91c2-109">If an assembly has information in the culture attribute, it must be in a subdirectory under the application directory with that culture's name.</span></span>

- <span data-ttu-id="a91c2-110">Глобальный кэш сборок.</span><span class="sxs-lookup"><span data-stu-id="a91c2-110">The global assembly cache.</span></span>

     <span data-ttu-id="a91c2-111">Это кэш кода уровня компьютера, который имеется на любом компьютере с установленной средой CLR.</span><span class="sxs-lookup"><span data-stu-id="a91c2-111">This is a machine-wide code cache that is installed wherever the common language runtime is installed.</span></span> <span data-ttu-id="a91c2-112">В большинстве случаев при необходимости совместного использования сборки в нескольких приложениях ее следует расположить в глобальном кэше сборок.</span><span class="sxs-lookup"><span data-stu-id="a91c2-112">In most cases, if you intend to share an assembly with multiple applications, you should deploy it into the global assembly cache.</span></span>

- <span data-ttu-id="a91c2-113">На HTTP-сервере.</span><span class="sxs-lookup"><span data-stu-id="a91c2-113">On an HTTP server.</span></span>

     <span data-ttu-id="a91c2-114">Сборка, развернутая на HTTP-сервере, должна иметь строгое имя; в разделе базы кода файла конфигурации приложения должно присутствовать указание на сборку.</span><span class="sxs-lookup"><span data-stu-id="a91c2-114">An assembly deployed on an HTTP server must have a strong name; you point to the assembly in the codebase section of the application's configuration file.</span></span>

## <a name="see-also"></a><span data-ttu-id="a91c2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="a91c2-115">See also</span></span>

- [<span data-ttu-id="a91c2-116">Создание сборок</span><span class="sxs-lookup"><span data-stu-id="a91c2-116">Create assemblies</span></span>](create.md)
- [<span data-ttu-id="a91c2-117">Глобальный кэш сборок</span><span class="sxs-lookup"><span data-stu-id="a91c2-117">Global assembly cache</span></span>](../../framework/app-domains/gac.md)
- [<span data-ttu-id="a91c2-118">Обнаружение сборок в среде выполнения</span><span class="sxs-lookup"><span data-stu-id="a91c2-118">How the runtime locates assemblies</span></span>](../../framework/deployment/how-the-runtime-locates-assemblies.md)
