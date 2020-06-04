---
title: Ограничения
ms.date: 07/20/2015
helpviewer_keywords:
- limits
- limitations [Visual Basic]
- limitations
- limits, Visual Basic code
- Visual Basic code, limitations
ms.assetid: cf1646b7-5d24-48c6-9616-bda8a4849d91
ms.openlocfilehash: 46294b68bda8a5d2d21c0e4efea6a78e6a265ffe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403191"
---
# <a name="visual-basic-limitations"></a><span data-ttu-id="8f4b4-102">Ограничения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f4b4-102">Visual Basic Limitations</span></span>
<span data-ttu-id="8f4b4-103">Более ранние версии Visual Basic принудительно применяют границы кода, такие как длина имен переменных, количество переменных, допустимых в модулях, и размер модуля.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-103">Earlier versions of Visual Basic enforced boundaries in code, such as the length of variable names, the number of variables allowed in modules, and module size.</span></span> <span data-ttu-id="8f4b4-104">В Visual Basic .NET эти ограничения были ослаблены, что обеспечивает большую свободу при написании и упорядочении кода.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-104">In Visual Basic .NET, these restrictions have been relaxed, giving you greater freedom in writing and arranging your code.</span></span>  
  
 <span data-ttu-id="8f4b4-105">Физические ограничения зависят больше от объема памяти во время выполнения, чем в вопросах времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-105">Physical limits are dependent more on run-time memory than on compile-time considerations.</span></span> <span data-ttu-id="8f4b4-106">Если вы используете разумные методики программирования и разбиваете крупные приложения на несколько классов и модулей, то вероятность возникновения внутренних ограничений на Visual Basic невелика.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-106">If you use prudent programming practices, and divide large applications into multiple classes and modules, then there is very little chance of encountering an internal Visual Basic limitation.</span></span>  
  
 <span data-ttu-id="8f4b4-107">Ниже перечислены некоторые ограничения, которые могут возникнуть в экстремальных случаях.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-107">The following are some limitations that you might encounter in extreme cases:</span></span>  
  
- <span data-ttu-id="8f4b4-108">**Длина имени.**</span><span class="sxs-lookup"><span data-stu-id="8f4b4-108">**Name Length.**</span></span> <span data-ttu-id="8f4b4-109">Существует максимальное число символов в имени каждого объявленного программного элемента.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-109">There is a maximum number of characters for the name of every declared programming element.</span></span> <span data-ttu-id="8f4b4-110">Это максимальное значение применяется ко всей уточняющей строке, если имя элемента является полным.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-110">This maximum applies to an entire qualification string if the element name is qualified.</span></span> <span data-ttu-id="8f4b4-111">См. раздел [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="8f4b4-111">See [Declared Element Names](../language-features/declared-elements/declared-element-names.md).</span></span>  
  
- <span data-ttu-id="8f4b4-112">**Длина строки.**</span><span class="sxs-lookup"><span data-stu-id="8f4b4-112">**Line Length.**</span></span> <span data-ttu-id="8f4b4-113">В физической строке исходного кода содержится не более 65535 символов.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-113">There is a maximum of 65535 characters in a physical line of source code.</span></span> <span data-ttu-id="8f4b4-114">Логическая строка исходного кода может быть длиннее, если используются символы продолжения строки.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-114">The logical source code line can be longer if you use line continuation characters.</span></span> <span data-ttu-id="8f4b4-115">См. раздел [как разрывать и объединять операторы в коде](how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="8f4b4-115">See [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
- <span data-ttu-id="8f4b4-116">**Размеры массива.**</span><span class="sxs-lookup"><span data-stu-id="8f4b4-116">**Array Dimensions.**</span></span> <span data-ttu-id="8f4b4-117">Существует максимальное количество измерений, которые можно объявить для массива.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-117">There is a maximum number of dimensions you can declare for an array.</span></span> <span data-ttu-id="8f4b4-118">Это ограничивает количество индексов, которые можно использовать для указания элемента массива.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-118">This limits how many indexes you can use to specify an array element.</span></span> <span data-ttu-id="8f4b4-119">См. раздел [измерения массива в Visual Basic](../language-features/arrays/array-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="8f4b4-119">See [Array Dimensions in Visual Basic](../language-features/arrays/array-dimensions.md).</span></span>  
  
- <span data-ttu-id="8f4b4-120">**Длина строки.**</span><span class="sxs-lookup"><span data-stu-id="8f4b4-120">**String Length.**</span></span> <span data-ttu-id="8f4b4-121">Существует максимальное число символов Юникода, которые можно хранить в одной строке.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-121">There is a maximum number of Unicode characters you can store in a single string.</span></span> <span data-ttu-id="8f4b4-122">См. [строковый тип данных](../../language-reference/data-types/string-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="8f4b4-122">See [String Data Type](../../language-reference/data-types/string-data-type.md).</span></span>  
  
- <span data-ttu-id="8f4b4-123">**Длина строки окружения.**</span><span class="sxs-lookup"><span data-stu-id="8f4b4-123">**Environment String Length.**</span></span> <span data-ttu-id="8f4b4-124">Для любой строки среды, используемой в качестве аргумента командной строки, можно использовать не более 32768 символов.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-124">There is a maximum of 32768 characters for any environment string used as a command-line argument.</span></span> <span data-ttu-id="8f4b4-125">Это ограничение на всех платформах.</span><span class="sxs-lookup"><span data-stu-id="8f4b4-125">This is a limitation on all platforms.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4b4-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8f4b4-126">See also</span></span>

- [<span data-ttu-id="8f4b4-127">Соглашения о структуре программы и коде</span><span class="sxs-lookup"><span data-stu-id="8f4b4-127">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="8f4b4-128">Соглашения об именах Visual Basic</span><span class="sxs-lookup"><span data-stu-id="8f4b4-128">Visual Basic Naming Conventions</span></span>](naming-conventions.md)
