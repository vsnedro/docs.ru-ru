---
title: Типы методов для работы со строками
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
ms.openlocfilehash: aba9af9c699cf8d07862c5d2967902bec1623500
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363763"
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a><span data-ttu-id="fa056-102">Типы методов для работы со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa056-102">Types of String Manipulation Methods in Visual Basic</span></span>
<span data-ttu-id="fa056-103">Существует несколько различных способов анализа строк и управления ими.</span><span class="sxs-lookup"><span data-stu-id="fa056-103">There are several different ways to analyze and manipulate your strings.</span></span> <span data-ttu-id="fa056-104">Некоторые методы являются частью языка Visual Basic, а другие — в `String` классе.</span><span class="sxs-lookup"><span data-stu-id="fa056-104">Some of the methods are a part of the Visual Basic language, and others are inherent in the `String` class.</span></span>  
  
## <a name="visual-basic-language-and-the-net-framework"></a><span data-ttu-id="fa056-105">Язык Visual Basic и .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fa056-105">Visual Basic Language and the .NET Framework</span></span>  
 <span data-ttu-id="fa056-106">Visual Basic методы используются в качестве встроенных функций языка.</span><span class="sxs-lookup"><span data-stu-id="fa056-106">Visual Basic methods are used as inherent functions of the language.</span></span> <span data-ttu-id="fa056-107">Они могут использоваться без уточнения в коде.</span><span class="sxs-lookup"><span data-stu-id="fa056-107">They may be used without qualification in your code.</span></span> <span data-ttu-id="fa056-108">В следующем примере показано типичное использование Visual Basic команды обработки строк:</span><span class="sxs-lookup"><span data-stu-id="fa056-108">The following example shows typical use of a Visual Basic string-manipulation command:</span></span>  
  
 [!code-vb[VbVbalrStrings#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#44)]  
  
 <span data-ttu-id="fa056-109">В этом примере `Mid` функция выполняет прямую операцию над `aString` и присваивает значение `bString` .</span><span class="sxs-lookup"><span data-stu-id="fa056-109">In this example, the `Mid` function performs a direct operation on `aString` and assigns the value to `bString`.</span></span>  
  
 <span data-ttu-id="fa056-110">Список методов обработки строк Visual Basic см. в разделе [Сводка манипулирования строками](../../../language-reference/keywords/string-manipulation-summary.md).</span><span class="sxs-lookup"><span data-stu-id="fa056-110">For a list of Visual Basic string manipulation methods, see [String Manipulation Summary](../../../language-reference/keywords/string-manipulation-summary.md).</span></span>  
  
### <a name="shared-methods-and-instance-methods"></a><span data-ttu-id="fa056-111">Общие методы и методы экземпляров</span><span class="sxs-lookup"><span data-stu-id="fa056-111">Shared Methods and Instance Methods</span></span>  
 <span data-ttu-id="fa056-112">Можно также управлять строками с помощью методов `String` класса.</span><span class="sxs-lookup"><span data-stu-id="fa056-112">You can also manipulate strings with the methods of the `String` class.</span></span> <span data-ttu-id="fa056-113">В существуют два типа методов `String` : *Общие* методы и методы *экземпляра* .</span><span class="sxs-lookup"><span data-stu-id="fa056-113">There are two types of methods in `String`: *shared* methods and *instance* methods.</span></span>  
  
#### <a name="shared-methods"></a><span data-ttu-id="fa056-114">Общие методы</span><span class="sxs-lookup"><span data-stu-id="fa056-114">Shared Methods</span></span>  
 <span data-ttu-id="fa056-115">Общий метод — это метод, который является производным от `String` самого класса и не требует работы экземпляра этого класса.</span><span class="sxs-lookup"><span data-stu-id="fa056-115">A shared method is a method that stems from the `String` class itself and does not require an instance of that class to work.</span></span> <span data-ttu-id="fa056-116">Эти методы можно уточнять именем класса ( `String` ), а не экземпляром `String` класса.</span><span class="sxs-lookup"><span data-stu-id="fa056-116">These methods can be qualified with the name of the class (`String`) rather than with an instance of the `String` class.</span></span> <span data-ttu-id="fa056-117">Пример:</span><span class="sxs-lookup"><span data-stu-id="fa056-117">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#45)]  
  
 <span data-ttu-id="fa056-118">В предыдущем примере <xref:System.String.Copy%2A?displayProperty=nameWithType> метод является статическим методом, который действует на заданное выражение и присваивает результирующее значение `bString` .</span><span class="sxs-lookup"><span data-stu-id="fa056-118">In the preceding example, the <xref:System.String.Copy%2A?displayProperty=nameWithType> method is a static method, which acts upon an expression it is given and assigns the resulting value to `bString`.</span></span>  
  
#### <a name="instance-methods"></a><span data-ttu-id="fa056-119">Методы экземпляра</span><span class="sxs-lookup"><span data-stu-id="fa056-119">Instance Methods</span></span>  
 <span data-ttu-id="fa056-120">Методы экземпляра, напротив, имеют определенный экземпляр `String` и должны уточняться именем экземпляра.</span><span class="sxs-lookup"><span data-stu-id="fa056-120">Instance methods, by contrast, stem from a particular instance of `String` and must be qualified with the instance name.</span></span> <span data-ttu-id="fa056-121">Пример:</span><span class="sxs-lookup"><span data-stu-id="fa056-121">For example:</span></span>  
  
 [!code-vb[VbVbalrStrings#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#46)]  
  
 <span data-ttu-id="fa056-122">В этом примере <xref:System.String.Substring%2A?displayProperty=nameWithType> метод является методом экземпляра `String` (то есть `aString` ).</span><span class="sxs-lookup"><span data-stu-id="fa056-122">In this example, the <xref:System.String.Substring%2A?displayProperty=nameWithType> method is a method of the instance of `String` (that is, `aString`).</span></span> <span data-ttu-id="fa056-123">Он выполняет операцию над `aString` и присваивает этому значению значение `bString` .</span><span class="sxs-lookup"><span data-stu-id="fa056-123">It performs an operation on `aString` and assigns that value to `bString`.</span></span>  
  
 <span data-ttu-id="fa056-124">Дополнительные сведения см. в документации по <xref:System.String> классу.</span><span class="sxs-lookup"><span data-stu-id="fa056-124">For more information, see the documentation for the <xref:System.String> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa056-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="fa056-125">See also</span></span>

- [<span data-ttu-id="fa056-126">Знакомство со строками в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fa056-126">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
