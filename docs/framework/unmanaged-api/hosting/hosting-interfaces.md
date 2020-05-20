---
title: Интерфейсы размещения
ms.date: 03/30/2017
helpviewer_keywords:
- interfaces [.NET Framework hosting]
- hosting interfaces [.NET Framework]
- unmanaged interfaces [.NET Framework], hosting
ms.assetid: cc64cb05-38da-418e-815a-daac8e8e26e5
ms.openlocfilehash: d1668f52ff305ec36fb520c7828c822537da0d02
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616103"
---
# <a name="hosting-interfaces"></a><span data-ttu-id="c0452-102">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="c0452-102">Hosting Interfaces</span></span>
<span data-ttu-id="c0452-103">В этом разделе описываются интерфейсы, которые неуправляемые узлы могут использовать для интеграции среды CLR в свои приложения.</span><span class="sxs-lookup"><span data-stu-id="c0452-103">This section describes the interfaces that unmanaged hosts can use to integrate the common language runtime (CLR) into their applications.</span></span>  
  
 <span data-ttu-id="c0452-104">Интерфейсы размещения .NET Framework версии 2,0 заменяют интерфейсы .NET Framework версии 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="c0452-104">The .NET Framework version 2.0 hosting interfaces supersede the .NET Framework version 1.0 and 1.1 interfaces.</span></span> <span data-ttu-id="c0452-105">Между двумя наборами интерфейсов существуют значительные различия.</span><span class="sxs-lookup"><span data-stu-id="c0452-105">There are significant differences between the two sets of interfaces.</span></span> <span data-ttu-id="c0452-106">Смешивание этих параметров может привести к непредвиденному поведению и не рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="c0452-106">Mixing them could cause unexpected behavior and is not recommended.</span></span>  
  
 <span data-ttu-id="c0452-107">.NET Framework версии 3,0 и 3,5 используют интерфейсы размещения .NET Framework версии 2,0 и не предоставляют никаких функций размещения.</span><span class="sxs-lookup"><span data-stu-id="c0452-107">The .NET Framework versions 3.0 and 3.5 use the .NET Framework version 2.0 hosting interfaces, and do not introduce any hosting features.</span></span>  
  
 <span data-ttu-id="c0452-108">Интерфейсы размещения .NET Framework 4 заменяют интерфейсы .NET Framework 2,0.</span><span class="sxs-lookup"><span data-stu-id="c0452-108">The .NET Framework 4 hosting interfaces supersede the .NET Framework 2.0 interfaces.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c0452-109">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="c0452-109">In This Section</span></span>  
 [<span data-ttu-id="c0452-110">Устаревшие интерфейсы размещения CLR и CoClasses</span><span class="sxs-lookup"><span data-stu-id="c0452-110">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 <span data-ttu-id="c0452-111">Описание интерфейсов размещения, представленных в .NET Framework версиях 1,0 и 1,1.</span><span class="sxs-lookup"><span data-stu-id="c0452-111">Describes the hosting interfaces introduced in the .NET Framework versions 1.0 and 1.1.</span></span>  
  
 [<span data-ttu-id="c0452-112">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c0452-112">CLR Hosting Interfaces</span></span>](clr-hosting-interfaces.md)  
 <span data-ttu-id="c0452-113">Описание интерфейсов размещения, представленных в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="c0452-113">Describes the hosting interfaces introduced in the .NET Framework version 2.0.</span></span>  
  
 [<span data-ttu-id="c0452-114">Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5</span><span class="sxs-lookup"><span data-stu-id="c0452-114">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 <span data-ttu-id="c0452-115">Описание интерфейсов размещения, появившихся в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="c0452-115">Describes the hosting interfaces introduced in the .NET Framework 4.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c0452-116">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="c0452-116">Related Sections</span></span>  
 [<span data-ttu-id="c0452-117">Размещение коклассов</span><span class="sxs-lookup"><span data-stu-id="c0452-117">Hosting Coclasses</span></span>](hosting-coclasses.md)  
  
 [<span data-ttu-id="c0452-118">Устаревшие функции размещения CLR</span><span class="sxs-lookup"><span data-stu-id="c0452-118">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)  
  
 [<span data-ttu-id="c0452-119">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="c0452-119">Hosting Enumerations</span></span>](hosting-enumerations.md)  
  
 [<span data-ttu-id="c0452-120">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="c0452-120">Hosting Structures</span></span>](hosting-structures.md)  
  
 [<span data-ttu-id="c0452-121">Размещение</span><span class="sxs-lookup"><span data-stu-id="c0452-121">Hosting</span></span>](index.md)  
  
 <span data-ttu-id="c0452-122">[Хост-приложения среды выполнения](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="c0452-122">[Runtime Hosts](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))</span></span>
