---
title: Практическое руководство. Создание нового метода для перечисления (руководство по программированию на C#)
description: Узнайте, как использовать методы расширения для добавления функциональных возможностей в перечисление в C#. В этом примере показан метод расширения Passing для перечисления Grades.
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [C#]
- extension methods [C#], for enums
- enum extensibility [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 100106f9-1e54-462c-8ebe-3892fe23b6eb
ms.openlocfilehash: 862eb86a5b0cc6b95302260874222bbc09d98132
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099416"
---
# <a name="how-to-create-a-new-method-for-an-enumeration-c-programming-guide"></a><span data-ttu-id="c44a8-104">Практическое руководство. Создание нового метода для перечисления (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c44a8-104">How to create a new method for an enumeration (C# Programming Guide)</span></span>

<span data-ttu-id="c44a8-105">Методы расширения позволяют добавить функциональные возможности, характерные для определенного типа перечисления.</span><span class="sxs-lookup"><span data-stu-id="c44a8-105">You can use extension methods to add functionality specific to a particular enum type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c44a8-106">Пример</span><span class="sxs-lookup"><span data-stu-id="c44a8-106">Example</span></span>  

 <span data-ttu-id="c44a8-107">В следующем примере перечисление `Grades` содержит возможные буквенные оценки, которые учащийся может получить в классе.</span><span class="sxs-lookup"><span data-stu-id="c44a8-107">In the following example, the `Grades` enumeration represents the possible letter grades that a student may receive in a class.</span></span> <span data-ttu-id="c44a8-108">Метод расширения с именем `Passing` добавляется в тип `Grades`, чтобы каждый экземпляр этого типа "знал", проходной это балл или нет.</span><span class="sxs-lookup"><span data-stu-id="c44a8-108">An extension method named `Passing` is added to the `Grades` type so that each instance of that type now "knows" whether it represents a passing grade or not.</span></span>  
  
 [!code-csharp[csProgGuideExtensionMethods#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExtensionMethods/cs/extensionmethods.cs#2)]  
  
 <span data-ttu-id="c44a8-109">Обратите внимание на то, что класс `Extensions` также содержит статическую переменную, которая обновляется динамически, а возвращаемое значение метода расширения отражает текущее значение этой переменной.</span><span class="sxs-lookup"><span data-stu-id="c44a8-109">Note that the `Extensions` class also contains a static variable that is updated dynamically and that the return value of the extension method reflects the current value of that variable.</span></span> <span data-ttu-id="c44a8-110">Это показывает, что в фоновом режиме методы расширения вызываются непосредственно для статического класса, в котором они определены.</span><span class="sxs-lookup"><span data-stu-id="c44a8-110">This demonstrates that, behind the scenes, extension methods are invoked directly on the static class in which they are defined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44a8-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c44a8-111">See also</span></span>

- [<span data-ttu-id="c44a8-112">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c44a8-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c44a8-113">Методы расширения</span><span class="sxs-lookup"><span data-stu-id="c44a8-113">Extension Methods</span></span>](./extension-methods.md)
