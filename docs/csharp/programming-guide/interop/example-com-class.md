---
title: Руководство по программированию на C#. Пример COM-класса
description: Узнайте, как предоставить класс в качестве COM-объекта в C#. Этот пример добавляет код в CS-файлы проекта и определяет свойство регистрации для COM-взаимодействия.
ms.date: 07/20/2015
helpviewer_keywords:
- examples [C#], COM classes
- COM, exposing Visual C# objects to
ms.assetid: 6504dea9-ad1c-4993-a794-830fec5270af
ms.openlocfilehash: d49d391f5ea7717e0c36782be65cfb2ae154b843
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90542800"
---
# <a name="example-com-class-c-programming-guide"></a><span data-ttu-id="9c499-104">Пример COM-класса (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="9c499-104">Example COM Class (C# Programming Guide)</span></span>
<span data-ttu-id="9c499-105">Далее приведен пример класса, который можно предоставить в качестве COM-объекта.</span><span class="sxs-lookup"><span data-stu-id="9c499-105">The following is an example of a class that you would expose as a COM object.</span></span> <span data-ttu-id="9c499-106">После помещения этого кода в CS-файл и добавления в проект свойства **Регистрация для COM-взаимодействия** необходимо присвоить значение **Истина**.</span><span class="sxs-lookup"><span data-stu-id="9c499-106">After this code has been placed in a .cs file and added to your project, set the **Register for COM Interop** property to **True**.</span></span> <span data-ttu-id="9c499-107">Дополнительные сведения см. в разделе [Практическое руководство. Register a Component for COM Interop](/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)) (Практическое руководство. Регистрация компонента для COM-взаимодействия).</span><span class="sxs-lookup"><span data-stu-id="9c499-107">For more information, see [How to: Register a Component for COM Interop](/previous-versions/visualstudio/visual-studio-2010/w29wacsy(v=vs.100)).</span></span>
  
 <span data-ttu-id="9c499-108">Предоставление объектов Visual C# для COM требует объявления интерфейса класса, интерфейса событий (если необходимо) и самого класса.</span><span class="sxs-lookup"><span data-stu-id="9c499-108">Exposing Visual C# objects to COM requires declaring a class interface, an events interface if it is required, and the class itself.</span></span> <span data-ttu-id="9c499-109">Члены класса должны соответствовать указанным ниже правилам, чтобы стать доступными для COM.</span><span class="sxs-lookup"><span data-stu-id="9c499-109">Class members must follow these rules to be visible to COM:</span></span>  
  
- <span data-ttu-id="9c499-110">Класс должен быть открытым.</span><span class="sxs-lookup"><span data-stu-id="9c499-110">The class must be public.</span></span>  
  
- <span data-ttu-id="9c499-111">Свойства, методы и события должны быть открытыми.</span><span class="sxs-lookup"><span data-stu-id="9c499-111">Properties, methods, and events must be public.</span></span>  
  
- <span data-ttu-id="9c499-112">Свойства и методы должны быть объявлены в интерфейсе класса.</span><span class="sxs-lookup"><span data-stu-id="9c499-112">Properties and methods must be declared on the class interface.</span></span>  
  
- <span data-ttu-id="9c499-113">События должны быть объявлены в интерфейсе событий.</span><span class="sxs-lookup"><span data-stu-id="9c499-113">Events must be declared in the event interface.</span></span>  
  
 <span data-ttu-id="9c499-114">Другие открытые элементы в классе, которые не объявлены в этих интерфейсах, не будут доступны для COM, но будут доступны другим объектам .NET.</span><span class="sxs-lookup"><span data-stu-id="9c499-114">Other public members in the class that are not declared in these interfaces will not be visible to COM, but they will be visible to other .NET objects.</span></span>  
  
 <span data-ttu-id="9c499-115">Чтобы предоставить свойства и методы COM, их необходимо объявить в интерфейсе класса, пометить атрибутом `DispId` и реализовать в классе.</span><span class="sxs-lookup"><span data-stu-id="9c499-115">To expose properties and methods to COM, you must declare them on the class interface and mark them with a `DispId` attribute, and implement them in the class.</span></span> <span data-ttu-id="9c499-116">Порядок объявления членов в интерфейсе — это порядок, используемый для виртуальной таблицы COM.</span><span class="sxs-lookup"><span data-stu-id="9c499-116">The order in which the members are declared in the interface is the order used for the COM vtable.</span></span>  
  
 <span data-ttu-id="9c499-117">Чтобы предоставить события из класса, их необходимо объявить в интерфейсе событий и пометить атрибутом `DispId`.</span><span class="sxs-lookup"><span data-stu-id="9c499-117">To expose events from your class, you must declare them on the events interface and mark them with a `DispId` attribute.</span></span> <span data-ttu-id="9c499-118">Класс не должен реализовывать этот интерфейс.</span><span class="sxs-lookup"><span data-stu-id="9c499-118">The class should not implement this interface.</span></span>  
  
 <span data-ttu-id="9c499-119">Класс реализует интерфейс класса; он может реализовывать несколько интерфейсов, но первой реализацией будет интерфейс класса по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9c499-119">The class implements the class interface; it can implement more than one interface, but the first implementation will be the default class interface.</span></span> <span data-ttu-id="9c499-120">Реализуйте методы и свойства, доступные модели COM здесь.</span><span class="sxs-lookup"><span data-stu-id="9c499-120">Implement the methods and properties exposed to COM here.</span></span> <span data-ttu-id="9c499-121">Они должны быть помечены как открытые и соответствовать объявлениям в интерфейсе класса.</span><span class="sxs-lookup"><span data-stu-id="9c499-121">They must be marked public and must match the declarations in the class interface.</span></span> <span data-ttu-id="9c499-122">Кроме того, объявите здесь события, инициируемые классом.</span><span class="sxs-lookup"><span data-stu-id="9c499-122">Also, declare the events raised by the class here.</span></span> <span data-ttu-id="9c499-123">Они должны быть помечены как открытые и соответствовать объявлениям в интерфейсе событий.</span><span class="sxs-lookup"><span data-stu-id="9c499-123">They must be marked public and must match the declarations in the events interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9c499-124">Пример</span><span class="sxs-lookup"><span data-stu-id="9c499-124">Example</span></span>  
 [!code-csharp[csProgGuideInterop#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInterop/CS/ExampleCOM.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="9c499-125">См. также</span><span class="sxs-lookup"><span data-stu-id="9c499-125">See also</span></span>

- [<span data-ttu-id="9c499-126">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="9c499-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="9c499-127">Взаимодействие</span><span class="sxs-lookup"><span data-stu-id="9c499-127">Interoperability</span></span>](./index.md)
- [<span data-ttu-id="9c499-128">Страница "Сборка" в конструкторе проектов (C#)</span><span class="sxs-lookup"><span data-stu-id="9c499-128">Build Page, Project Designer (C#)</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)
