---
title: Практическое руководство. Создание нового метода для перечисления (руководство по программированию на C#)
description: Узнайте, как использовать методы расширения для добавления функциональных возможностей в перечисление в C#. В этом примере показан метод расширения Passing для перечисления Grades.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 6c01a73476e98e8344a7a8dc35a5fd80384fc7a2
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864492"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="f2236-104">Практическое руководство. Создание нового метода для перечисления (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="f2236-104">How to create a new method for an enumeration (C# Programming Guide)</span></span>
<span data-ttu-id="f2236-105">Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="f2236-105">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f2236-106">Пример</span><span class="sxs-lookup"><span data-stu-id="f2236-106">Example</span></span>  
 <span data-ttu-id="f2236-107">В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе.</span><span class="sxs-lookup"><span data-stu-id="f2236-107">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="f2236-108">Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.</span><span class="sxs-lookup"><span data-stu-id="f2236-108">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="f2236-109">Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной.</span><span class="sxs-lookup"><span data-stu-id="f2236-109">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="f2236-110">Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="f2236-110">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2236-111">См. также</span><span class="sxs-lookup"><span data-stu-id="f2236-111">See also</span></span>

- [<span data-ttu-id="f2236-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="f2236-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f2236-113">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="f2236-113">Extension Methods</span></span>](./extension-methods.md)
