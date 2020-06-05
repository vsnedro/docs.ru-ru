---
title: Практическое руководство. Хранение нескольких значений в переменной
ms.date: 07/20/2015
helpviewer_keywords:
- classes [Visual Basic], composite data types
- composite types [Visual Basic]
- composite data types [Visual Basic]
- data types [Visual Basic], composite
- arrays [Visual Basic], composite data types
- structures [Visual Basic], composite data types
- arrays [Visual Basic], compilation errors
- types [Visual Basic], composite
ms.assetid: 5fe0e558-aac2-4a40-b7f2-7cfea7336917
ms.openlocfilehash: 399c5909ee6988f96bcc85260b0401f3bd18a0f2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393900"
---
# <a name="how-to-hold-more-than-one-value-in-a-variable-visual-basic"></a><span data-ttu-id="626db-102">Практическое руководство. Хранение нескольких значений в переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="626db-102">How to: Hold More Than One Value in a Variable (Visual Basic)</span></span>

<span data-ttu-id="626db-103">Переменная содержит более одного значения, если объявить ее для *составного типа данных*.</span><span class="sxs-lookup"><span data-stu-id="626db-103">A variable holds more than one value if you declare it to be of a *composite data type*.</span></span>

<span data-ttu-id="626db-104">[Составные типы данных](composite-data-types.md) включают структуры, массивы и классы.</span><span class="sxs-lookup"><span data-stu-id="626db-104">[Composite Data Types](composite-data-types.md) include structures, arrays, and classes.</span></span> <span data-ttu-id="626db-105">Переменная составного типа данных может содержать сочетание простейших типов данных и других составных типов.</span><span class="sxs-lookup"><span data-stu-id="626db-105">A variable of a composite data type can hold a combination of elementary data types and other composite types.</span></span> <span data-ttu-id="626db-106">Структуры и классы могут содержать код и данные.</span><span class="sxs-lookup"><span data-stu-id="626db-106">Structures and classes can hold code as well as data.</span></span>

## <a name="to-hold-more-than-one-value-in-a-variable"></a><span data-ttu-id="626db-107">Хранение более одного значения в переменной</span><span class="sxs-lookup"><span data-stu-id="626db-107">To hold more than one value in a variable</span></span>

1. <span data-ttu-id="626db-108">Определите составной тип данных, который будет использоваться для переменной.</span><span class="sxs-lookup"><span data-stu-id="626db-108">Determine what composite data type you want to use for your variable.</span></span>

2. <span data-ttu-id="626db-109">Если составной тип данных еще не определен, определите его, чтобы переменная могла его использовать.</span><span class="sxs-lookup"><span data-stu-id="626db-109">If the composite data type is not already defined, define it so that your variable can use it.</span></span>

    - <span data-ttu-id="626db-110">Определите структуру с помощью [оператора Structure](../../../language-reference/statements/structure-statement.md).</span><span class="sxs-lookup"><span data-stu-id="626db-110">Define a structure with a [Structure Statement](../../../language-reference/statements/structure-statement.md).</span></span>

    - <span data-ttu-id="626db-111">Определите массив с помощью [оператора Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="626db-111">Define an array with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

    - <span data-ttu-id="626db-112">Определите класс с помощью [оператора класса](../../../language-reference/statements/class-statement.md).</span><span class="sxs-lookup"><span data-stu-id="626db-112">Define a class with a [Class Statement](../../../language-reference/statements/class-statement.md).</span></span>

3. <span data-ttu-id="626db-113">Объявите переменную с помощью `Dim` оператора.</span><span class="sxs-lookup"><span data-stu-id="626db-113">Declare your variable with a `Dim` statement.</span></span>

4. <span data-ttu-id="626db-114">Подпишите имя переменной с помощью `As` предложения.</span><span class="sxs-lookup"><span data-stu-id="626db-114">Follow the variable name with an `As` clause.</span></span>

5. <span data-ttu-id="626db-115">Используйте `As` ключевое слово с именем соответствующего составного типа данных.</span><span class="sxs-lookup"><span data-stu-id="626db-115">Follow the `As` keyword with the name of the appropriate composite data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="626db-116">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="626db-116">See also</span></span>

- [<span data-ttu-id="626db-117">Типы данных</span><span class="sxs-lookup"><span data-stu-id="626db-117">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="626db-118">Символы типов</span><span class="sxs-lookup"><span data-stu-id="626db-118">Type Characters</span></span>](type-characters.md)
- [<span data-ttu-id="626db-119">Составные типы данных</span><span class="sxs-lookup"><span data-stu-id="626db-119">Composite Data Types</span></span>](composite-data-types.md)
- [<span data-ttu-id="626db-120">Структуры</span><span class="sxs-lookup"><span data-stu-id="626db-120">Structures</span></span>](structures.md)
- [<span data-ttu-id="626db-121">Массивы</span><span class="sxs-lookup"><span data-stu-id="626db-121">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="626db-122">Объекты и классы</span><span class="sxs-lookup"><span data-stu-id="626db-122">Objects and Classes</span></span>](../objects-and-classes/index.md)
- [<span data-ttu-id="626db-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="626db-123">Value Types and Reference Types</span></span>](value-types-and-reference-types.md)
