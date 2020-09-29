---
title: Руководство по программированию на C#. Закрытые конструкторы
description: Закрытый конструктор — это особый конструктор экземпляров в C#, используемый для ограничения способа создания объекта. Он может использоваться с фабричными методами или другими идиомами конструирования.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, private constructors
- private constructors [C#]
ms.assetid: 29eeaa7d-8d81-453c-94b9-0e2800172621
ms.openlocfilehash: c6048424128b462bfc56d9c7c3cf8f75cca9298d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159349"
---
# <a name="private-constructors-c-programming-guide"></a><span data-ttu-id="fc55a-104">Закрытые конструкторы (Руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="fc55a-104">Private Constructors (C# Programming Guide)</span></span>

<span data-ttu-id="fc55a-105">Закрытый конструктор — это особый конструктор экземпляров.</span><span class="sxs-lookup"><span data-stu-id="fc55a-105">A private constructor is a special instance constructor.</span></span> <span data-ttu-id="fc55a-106">Обычно он используется в классах, содержащих только статические элементы.</span><span class="sxs-lookup"><span data-stu-id="fc55a-106">It is generally used in classes that contain static members only.</span></span> <span data-ttu-id="fc55a-107">Если в классе один или несколько закрытых конструкторов и ни одного открытого конструктора, то прочие классы (за исключением вложенных классов) не смогут создавать экземпляры этого класса.</span><span class="sxs-lookup"><span data-stu-id="fc55a-107">If a class has one or more private constructors and no public constructors, other classes (except nested classes) cannot create instances of this class.</span></span> <span data-ttu-id="fc55a-108">Пример:</span><span class="sxs-lookup"><span data-stu-id="fc55a-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideObjects#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#11)]  
  
 <span data-ttu-id="fc55a-109">Объявление пустого конструктора запрещает автоматическое создание конструктора без параметров.</span><span class="sxs-lookup"><span data-stu-id="fc55a-109">The declaration of the empty constructor prevents the automatic generation of a parameterless constructor.</span></span> <span data-ttu-id="fc55a-110">Обратите внимание, что если не использовать с конструктором модификатор доступа, то по умолчанию он все равно будет закрытым.</span><span class="sxs-lookup"><span data-stu-id="fc55a-110">Note that if you do not use an access modifier with the constructor it will still be private by default.</span></span> <span data-ttu-id="fc55a-111">Однако обычно используется модификатор [private](../../language-reference/keywords/private.md), чтобы явно обозначить невозможность создания экземпляров этого класса.</span><span class="sxs-lookup"><span data-stu-id="fc55a-111">However, the [private](../../language-reference/keywords/private.md) modifier is usually used explicitly to make it clear that the class cannot be instantiated.</span></span>  
  
 <span data-ttu-id="fc55a-112">Закрытые конструкторы используются, чтобы не допустить создания экземпляров класса при отсутствии полей или методов экземпляра, например для класса <xref:System.Math>, или когда осуществляется вызов метода для получения экземпляра класса.</span><span class="sxs-lookup"><span data-stu-id="fc55a-112">Private constructors are used to prevent creating instances of a class when there are no instance fields or methods, such as the <xref:System.Math> class, or when a method is called to obtain an instance of a class.</span></span> <span data-ttu-id="fc55a-113">Если все методы в классе являются статическими, имеет смысл сделать статическим весь класс.</span><span class="sxs-lookup"><span data-stu-id="fc55a-113">If all the methods in the class are static, consider making the complete class static.</span></span> <span data-ttu-id="fc55a-114">Дополнительные сведения см. в разделе [Статические классы и члены статических классов](./static-classes-and-static-class-members.md).</span><span class="sxs-lookup"><span data-stu-id="fc55a-114">For more information see [Static Classes and Static Class Members](./static-classes-and-static-class-members.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc55a-115">Пример</span><span class="sxs-lookup"><span data-stu-id="fc55a-115">Example</span></span>  

 <span data-ttu-id="fc55a-116">Ниже приведен пример класса с закрытым конструктором.</span><span class="sxs-lookup"><span data-stu-id="fc55a-116">The following is an example of a class using a private constructor.</span></span>  
  
 [!code-csharp[csProgGuideObjects#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#12)]  
  
 <span data-ttu-id="fc55a-117">Обратите внимание, что если в примере раскомментировать следующий оператор, возникнет ошибка, так как конструктор недоступен из-за уровня защиты:</span><span class="sxs-lookup"><span data-stu-id="fc55a-117">Notice that if you uncomment the following statement from the example, it will generate an error because the constructor is inaccessible because of its protection level:</span></span>  
  
 [!code-csharp[csProgGuideObjects#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#13)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fc55a-118">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="fc55a-118">C# Language Specification</span></span>  

<span data-ttu-id="fc55a-119">Дополнительные сведения см. в разделе [Закрытые конструкторы](~/_csharplang/spec/classes.md#private-constructors) в [Спецификации языка C#](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="fc55a-119">For more information, see [Private constructors](~/_csharplang/spec/classes.md#private-constructors) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="fc55a-120">Спецификация языка является предписывающим источником информации о синтаксисе и использовании языка C#.</span><span class="sxs-lookup"><span data-stu-id="fc55a-120">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fc55a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="fc55a-121">See also</span></span>

- [<span data-ttu-id="fc55a-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="fc55a-122">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fc55a-123">Классы и структуры</span><span class="sxs-lookup"><span data-stu-id="fc55a-123">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="fc55a-124">Конструкторы</span><span class="sxs-lookup"><span data-stu-id="fc55a-124">Constructors</span></span>](./constructors.md)
- [<span data-ttu-id="fc55a-125">Методы завершения</span><span class="sxs-lookup"><span data-stu-id="fc55a-125">Finalizers</span></span>](./destructors.md)
- [<span data-ttu-id="fc55a-126">private</span><span class="sxs-lookup"><span data-stu-id="fc55a-126">private</span></span>](../../language-reference/keywords/private.md)
- [<span data-ttu-id="fc55a-127">public</span><span class="sxs-lookup"><span data-stu-id="fc55a-127">public</span></span>](../../language-reference/keywords/public.md)
