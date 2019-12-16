---
title: "сборки и параллельное выполнение"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- side-by-side execution [.NET Framework]
- assemblies [.NET Framework], side-by-side execution
ms.assetid: e42036ee-7590-47d1-b884-cc856e39bd5d
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e39e30a75f4d75542c3fc034f3eb1acf1e5547d5
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="assemblies-and-side-by-side-execution"></a><span data-ttu-id="f0a43-102">сборки и параллельное выполнение</span><span class="sxs-lookup"><span data-stu-id="f0a43-102">Assemblies and Side-by-Side Execution</span></span>
<span data-ttu-id="f0a43-103">Под параллельным выполнением понимается возможность сохранения и выполнения нескольких версий приложения или компонента на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="f0a43-103">Side-by-side execution is the ability to store and execute multiple versions of an application or component on the same computer.</span></span> <span data-ttu-id="f0a43-104">Это означает, что одновременно на одном и том же компьютере в одно и то же время можно иметь несколько версий среды выполнения и несколько версий приложений и компонентов, использующих среду выполнения данной версии.</span><span class="sxs-lookup"><span data-stu-id="f0a43-104">This means that you can have multiple versions of the runtime, and multiple versions of applications and components that use a version of the runtime, on the same computer at the same time.</span></span> <span data-ttu-id="f0a43-105">Параллельное выполнение предоставляет дополнительные возможности выбора версий компонента, с которым связано приложение, а также дополнительные возможности выбора используемой приложением версии среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0a43-105">Side-by-side execution gives you more control over what versions of a component an application binds to, and more control over what version of the runtime an application uses.</span></span>  
  
 <span data-ttu-id="f0a43-106">Поддержка параллельного хранения и выполнения различных версий одной и той же сборки является неотъемлемой частью использования строгих имен. Эта поддержка встроена в инфраструктуру среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0a43-106">Support for side-by-side storage and execution of different versions of the same assembly is an integral part of strong naming and is built into the infrastructure of the runtime.</span></span> <span data-ttu-id="f0a43-107">Поскольку номер версии сборки со строгим именем является частью ее удостоверения, среда выполнения позволяет хранить несколько версий одной и той же сборки в глобальном кэше сборок и загружать эти сборки на этапе выполнения.</span><span class="sxs-lookup"><span data-stu-id="f0a43-107">Because the strong-named assembly's version number is part of its identity, the runtime can store multiple versions of the same assembly in the global assembly cache and load those assemblies at run time.</span></span>  
  
 <span data-ttu-id="f0a43-108">Хотя среда выполнения предоставляет возможность создавать параллельные приложения, параллельное выполнение не реализуется автоматически.</span><span class="sxs-lookup"><span data-stu-id="f0a43-108">Although the runtime provides you with the ability to create side-by-side applications, side-by-side execution is not automatic.</span></span> <span data-ttu-id="f0a43-109">Дополнительные сведения о создании приложений для параллельного выполнения см. в разделе [Рекомендации по созданию компонентов для параллельного выполнения](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span><span class="sxs-lookup"><span data-stu-id="f0a43-109">For more information on creating applications for side-by-side execution, see [Guidelines for Creating Components for Side-by-Side Execution](../../../docs/framework/deployment/guidelines-for-creating-components-for-side-by-side-execution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a43-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f0a43-110">See Also</span></span>  
 <span data-ttu-id="f0a43-111">[Обнаружение сборок в среде выполнения](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="f0a43-111">[How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md) </span></span>  
 [<span data-ttu-id="f0a43-112">Сборки в среде CLR</span><span class="sxs-lookup"><span data-stu-id="f0a43-112">Assemblies in the Common Language Runtime</span></span>](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)
