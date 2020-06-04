---
title: Директивы
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410001"
---
# <a name="directives-visual-basic"></a><span data-ttu-id="55b0b-102">Директивы (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55b0b-102">Directives (Visual Basic)</span></span>

<span data-ttu-id="55b0b-103">В подразделах этого раздела описаны директивы компилятора исходного кода Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="55b0b-103">The topics in this section document the Visual Basic source code compiler directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="55b0b-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="55b0b-104">In This Section</span></span>  

 <span data-ttu-id="55b0b-105">[Директива #Const](const-directive.md) — Определение константы компилятора</span><span class="sxs-lookup"><span data-stu-id="55b0b-105">[#Const Directive](const-directive.md) -- Define a compiler constant</span></span>  
  
 <span data-ttu-id="55b0b-106">[Директива #ExternalSource](externalsource-directive.md) — указывает сопоставление между исходными строками и текстом, внешним по отношению к источнику</span><span class="sxs-lookup"><span data-stu-id="55b0b-106">[#ExternalSource Directive](externalsource-directive.md) -- Indicate a mapping between source lines and text external to the source</span></span>  
  
 <span data-ttu-id="55b0b-107">[#If... Then... #Else директивы](if-then-else-directives.md) --компилировать выбранные блоки кода</span><span class="sxs-lookup"><span data-stu-id="55b0b-107">[#If...Then...#Else Directives](if-then-else-directives.md) -- Compile selected blocks of code</span></span>  
  
 <span data-ttu-id="55b0b-108">[Директива #Region](region-directive.md) — сворачивание и скрытие разделов кода в редакторе Visual Studio</span><span class="sxs-lookup"><span data-stu-id="55b0b-108">[#Region Directive](region-directive.md) -- Collapse and hide sections of code in the Visual Studio editor</span></span>  
  
 <span data-ttu-id="55b0b-109">**#Disable, #Enable** — отключение и включение конкретных предупреждений для регионов кода.</span><span class="sxs-lookup"><span data-stu-id="55b0b-109">**#Disable, #Enable** -- Disable and enable specific warnings for regions of code.</span></span>  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 <span data-ttu-id="55b0b-110">Можно также отключить и включить список кодов предупреждений с разделителями-запятыми.</span><span class="sxs-lookup"><span data-stu-id="55b0b-110">You can disable and enable a comma-separated list of warning codes too.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="55b0b-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="55b0b-111">Related Sections</span></span>  

 [<span data-ttu-id="55b0b-112">Справочник по языку Visual Basic</span><span class="sxs-lookup"><span data-stu-id="55b0b-112">Visual Basic Language Reference</span></span>](../index.md)  
  