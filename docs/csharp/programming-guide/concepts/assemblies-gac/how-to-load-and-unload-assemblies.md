---
title: "Практическое руководство. Загрузка и выгрузка сборок (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 6a4f490f-3576-471f-9533-003737cad4a3
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6bf6de24f4cbc3f3bd855b6d2cafa8120ebd90ee
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-load-and-unload-assemblies-c"></a><span data-ttu-id="da880-102">Практическое руководство. Загрузка и выгрузка сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="da880-102">How to: Load and Unload Assemblies (C#)</span></span>
<span data-ttu-id="da880-103">Сборки, на которые ссылается программа, загружаются автоматически во время построения, но в текущий домен приложения можно также загрузить конкретные сборки во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="da880-103">The assemblies referenced by your program will automatically be loaded at build time, but it is also possible to load specific assemblies into the current application domain at runtime.</span></span> <span data-ttu-id="da880-104">Дополнительные сведения см. в разделе [Практическое руководство. Загрузка сборок в домен приложения](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="da880-104">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
 <span data-ttu-id="da880-105">Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится.</span><span class="sxs-lookup"><span data-stu-id="da880-105">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="da880-106">Даже если сборка не входит в область, фактический файл сборки остается загруженным до тех пор, пока не будут выгружены домены приложений с этой сборкой.</span><span class="sxs-lookup"><span data-stu-id="da880-106">Even if the assembly goes out of scope, the actual assembly file will remain loaded until all application domains that contain it are unloaded.</span></span>  
  
 <span data-ttu-id="da880-107">Если необходимо выгрузить только часть сборок, создайте новый домен приложения, выполните код внутри этого домена, а затем выгрузите этот домен приложения.</span><span class="sxs-lookup"><span data-stu-id="da880-107">If you want to unload some assemblies but not others, consider creating a new application domain, executing the code inside that domain, and then unloading that application domain.</span></span> <span data-ttu-id="da880-108">Дополнительные сведения см. в разделе [Практическое руководство. Выгрузка домена приложения](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="da880-108">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
### <a name="to-load-an-assembly-into-an-application-domain"></a><span data-ttu-id="da880-109">Загрузка сборки в домен приложения</span><span class="sxs-lookup"><span data-stu-id="da880-109">To load an assembly into an application domain</span></span>  
  
1.  <span data-ttu-id="da880-110">Используйте один из нескольких методов загрузки, содержащихся в классах <xref:System.AppDomain> и <xref:System.Reflection>.</span><span class="sxs-lookup"><span data-stu-id="da880-110">Use one of the several load methods contained in the classes <xref:System.AppDomain> and <xref:System.Reflection>.</span></span> <span data-ttu-id="da880-111">Дополнительные сведения см. в разделе [Практическое руководство. Загрузка сборок в домен приложения](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="da880-111">For more information, see [How to: Load Assemblies into an Application Domain](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md).</span></span>  
  
### <a name="to-unload-an-application-domain"></a><span data-ttu-id="da880-112">Выгрузка домена приложения</span><span class="sxs-lookup"><span data-stu-id="da880-112">To unload an application domain</span></span>  
  
1.  <span data-ttu-id="da880-113">Отдельную сборку нельзя выгрузить, не выгрузив все домены приложений, в которых она содержится.</span><span class="sxs-lookup"><span data-stu-id="da880-113">There is no way to unload an individual assembly without unloading all of the application domains that contain it.</span></span> <span data-ttu-id="da880-114">Используйте метод `Unload` из <xref:System.AppDomain> для выгрузки доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="da880-114">Use the `Unload` method from <xref:System.AppDomain> to unload the application domains.</span></span> <span data-ttu-id="da880-115">Дополнительные сведения см. в разделе [Практическое руководство. Выгрузка домена приложения](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span><span class="sxs-lookup"><span data-stu-id="da880-115">For more information, see [How to: Unload an Application Domain](../../../../framework/app-domains/how-to-unload-an-application-domain.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da880-116">См. также</span><span class="sxs-lookup"><span data-stu-id="da880-116">See Also</span></span>  
 <span data-ttu-id="da880-117">[Руководство по программированию на C#](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="da880-117">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="da880-118">[Сборки и глобальный кэш сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="da880-118">[Assemblies and the Global Assembly Cache (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
 [<span data-ttu-id="da880-119">Практическое руководство. Загрузка сборок в домен приложения</span><span class="sxs-lookup"><span data-stu-id="da880-119">How to: Load Assemblies into an Application Domain</span></span>](../../../../framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)
