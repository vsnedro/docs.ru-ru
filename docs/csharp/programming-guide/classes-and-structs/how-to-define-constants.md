---
title: Определение констант в C#
description: Узнайте, как определять константы в C#, которые являются полями, значения которых задаются во время компиляции. Используйте константы для присвоения значимых имен особым значениям.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, constants
- constants [C#]
ms.assetid: 43f511be-346c-4b8a-995e-aded94542ece
ms.openlocfilehash: afa2799cf76f976e332f91b631dc90e2799a0aa0
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864648"
---
# <a name="how-to-define-constants-in-c"></a><span data-ttu-id="9b821-104">Определение констант в C\#</span><span class="sxs-lookup"><span data-stu-id="9b821-104">How to define constants in C\#</span></span>
<span data-ttu-id="9b821-105">Константы — это поля, значения которых устанавливаются во время компиляции и не изменяются.</span><span class="sxs-lookup"><span data-stu-id="9b821-105">Constants are fields whose values are set at compile time and can never be changed.</span></span> <span data-ttu-id="9b821-106">С помощью констант можно присвоить особым значениям значащие имена вместо числовых литералов.</span><span class="sxs-lookup"><span data-stu-id="9b821-106">Use constants to provide meaningful names instead of numeric literals ("magic numbers") for special values.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9b821-107">В C# с помощью директивы препроцессора [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) нельзя определять константы так, как это было реализовано в C и C++.</span><span class="sxs-lookup"><span data-stu-id="9b821-107">In C# the [#define](../../language-reference/preprocessor-directives/preprocessor-define.md) preprocessor directive cannot be used to define constants in the way that is typically used in C and C++.</span></span>  
  
 <span data-ttu-id="9b821-108">Чтобы определить значения константы целочисленного типа (`int`, `byte` и т. д.), используйте перечисляемый тип.</span><span class="sxs-lookup"><span data-stu-id="9b821-108">To define constant values of integral types (`int`, `byte`, and so on) use an enumerated type.</span></span> <span data-ttu-id="9b821-109">Дополнительные сведения см. в разделе [Перечисление](../../language-reference/builtin-types/enum.md).</span><span class="sxs-lookup"><span data-stu-id="9b821-109">For more information, see [enum](../../language-reference/builtin-types/enum.md).</span></span>  
  
 <span data-ttu-id="9b821-110">Чтобы определить нецелочисленные константы, можно сгруппировать их в статический класс с именем `Constants`.</span><span class="sxs-lookup"><span data-stu-id="9b821-110">To define non-integral constants, one approach is to group them in a single static class named `Constants`.</span></span> <span data-ttu-id="9b821-111">В этом случае перед любыми ссылками на константы будет необходимо указывать имя класса, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="9b821-111">This will require that all references to the constants be prefaced with the class name, as shown in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b821-112">Пример</span><span class="sxs-lookup"><span data-stu-id="9b821-112">Example</span></span>  
 [!code-csharp[csProgGuideObjects#89](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#89)]  
  
 <span data-ttu-id="9b821-113">Используя квалификатор имени класса, вы гарантируете, что вы сами и другие разработчики будете понимать, что имеете дело с константой, которую нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="9b821-113">The use of the class name qualifier helps ensure that you and others who use the constant understand that it is constant and cannot be modified.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b821-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9b821-114">See also</span></span>

- [<span data-ttu-id="9b821-115">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="9b821-115">Classes and Structs</span></span>](./index.md)
