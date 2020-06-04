---
title: Практическое руководство. Присвоение одного массива другому
ms.date: 07/20/2015
helpviewer_keywords:
- covariance, arrays
- arrays [Visual Basic], assigning
- arrays [Visual Basic], covariance
ms.assetid: 1ae89ea5-f292-4282-bcfc-e9b06b37fbd5
ms.openlocfilehash: c38def1ba9f3720bc760d6f6e4264510c884c930
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413083"
---
# <a name="how-to-assign-one-array-to-another-array-visual-basic"></a><span data-ttu-id="8a06f-102">Практическое руководство. Присвоение одного массива другому (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a06f-102">How to: Assign One Array to Another Array (Visual Basic)</span></span>

<span data-ttu-id="8a06f-103">Поскольку массивы являются объектами, их можно использовать в инструкциях присваивания, например в других типах объектов.</span><span class="sxs-lookup"><span data-stu-id="8a06f-103">Because arrays are objects, you can use them in assignment statements like other object types.</span></span> <span data-ttu-id="8a06f-104">Переменная массива содержит указатель на данные, образующей элементы массива, и сведения о ранге и длине, и присваивание копирует только этот указатель.</span><span class="sxs-lookup"><span data-stu-id="8a06f-104">An array variable holds a pointer to the data constituting the array elements and the rank and length information, and an assignment copies only this pointer.</span></span>

### <a name="to-assign-one-array-to-another-array"></a><span data-ttu-id="8a06f-105">Назначение одного массива другому массиву</span><span class="sxs-lookup"><span data-stu-id="8a06f-105">To assign one array to another array</span></span>

1. <span data-ttu-id="8a06f-106">Убедитесь, что два массива имеют одинаковый ранг (число измерений) и совместимые типы данных элементов.</span><span class="sxs-lookup"><span data-stu-id="8a06f-106">Ensure that the two arrays have the same rank (number of dimensions) and compatible element data types.</span></span>

2. <span data-ttu-id="8a06f-107">Используйте стандартную инструкцию присваивания, чтобы присвоить исходный массив целевому массиву.</span><span class="sxs-lookup"><span data-stu-id="8a06f-107">Use a standard assignment statement to assign the source array to the destination array.</span></span> <span data-ttu-id="8a06f-108">Не используйте имя массива с круглыми скобками.</span><span class="sxs-lookup"><span data-stu-id="8a06f-108">Do not follow either array name with parentheses.</span></span>

    ```vb
    Dim formArray() As System.Windows.Forms.Form
    Dim controlArray() As System.Windows.Forms.Control
    controlArray = formArray
    ```

<span data-ttu-id="8a06f-109">При назначении одного массива другому применяются следующие правила.</span><span class="sxs-lookup"><span data-stu-id="8a06f-109">When you assign one array to another, the following rules apply:</span></span>

- <span data-ttu-id="8a06f-110">**Равные ранги.**</span><span class="sxs-lookup"><span data-stu-id="8a06f-110">**Equal Ranks.**</span></span> <span data-ttu-id="8a06f-111">Ранг (количество измерений) массива назначения должен быть таким же, как и у исходного массива.</span><span class="sxs-lookup"><span data-stu-id="8a06f-111">The rank (number of dimensions) of the destination array must be the same as that of the source array.</span></span>

  <span data-ttu-id="8a06f-112">При условии, что ранги двух массивов равны, измерения не обязательно должны быть равны.</span><span class="sxs-lookup"><span data-stu-id="8a06f-112">Provided the ranks of the two arrays are equal, the dimensions do not need to be equal.</span></span> <span data-ttu-id="8a06f-113">Количество элементов в заданном измерении может изменяться во время назначения.</span><span class="sxs-lookup"><span data-stu-id="8a06f-113">The number of elements in a given dimension can change during assignment.</span></span>

- <span data-ttu-id="8a06f-114">**Типы элементов.**</span><span class="sxs-lookup"><span data-stu-id="8a06f-114">**Element Types.**</span></span> <span data-ttu-id="8a06f-115">Оба массива должны иметь элементы *ссылочного типа* либо оба массива должны иметь элементы *типа значения* .</span><span class="sxs-lookup"><span data-stu-id="8a06f-115">Either both arrays must have *reference type* elements or both arrays must have *value type* elements.</span></span> <span data-ttu-id="8a06f-116">Дополнительные сведения см. в разделе [типы значений и ссылочные типы](../data-types/value-types-and-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="8a06f-116">For more information, see [Value Types and Reference Types](../data-types/value-types-and-reference-types.md).</span></span>

  - <span data-ttu-id="8a06f-117">Если оба массива имеют элементы типа значения, то типы данных элементов должны быть одинаковыми.</span><span class="sxs-lookup"><span data-stu-id="8a06f-117">If both arrays have value type elements, the element data types must be exactly the same.</span></span> <span data-ttu-id="8a06f-118">Единственным исключением является то, что массив элементов можно назначить `Enum` массиву базового типа `Enum` .</span><span class="sxs-lookup"><span data-stu-id="8a06f-118">The only exception to this is that you can assign an array of `Enum` elements to an array of the base type of that `Enum`.</span></span>

  - <span data-ttu-id="8a06f-119">Если оба массива имеют элементы ссылочного типа, тип исходного элемента должен быть производным от типа целевого элемента.</span><span class="sxs-lookup"><span data-stu-id="8a06f-119">If both arrays have reference type elements, the source element type must derive from the destination element type.</span></span> <span data-ttu-id="8a06f-120">В этом случае два массива имеют те же отношения наследования, что и их элементы.</span><span class="sxs-lookup"><span data-stu-id="8a06f-120">When this is the case, the two arrays have the same inheritance relationship as their elements.</span></span> <span data-ttu-id="8a06f-121">Это называется *ковариацией массивов*.</span><span class="sxs-lookup"><span data-stu-id="8a06f-121">This is called *array covariance*.</span></span>

<span data-ttu-id="8a06f-122">Компилятор сообщает об ошибке, если приведенные выше правила нарушаются, например, если типы данных несовместимы или ранги не равны.</span><span class="sxs-lookup"><span data-stu-id="8a06f-122">The compiler reports an error if the above rules are violated, for example if the data types are not compatible or the ranks are unequal.</span></span> <span data-ttu-id="8a06f-123">В код можно добавить обработку ошибок, чтобы убедиться, что массивы совместимы, прежде чем пытаться выполнить назначение.</span><span class="sxs-lookup"><span data-stu-id="8a06f-123">You can add error handling to your code to make sure that the arrays are compatible before attempting an assignment.</span></span> <span data-ttu-id="8a06f-124">Можно также использовать ключевое слово [оператора TryCast](../../../language-reference/operators/trycast-operator.md) , если необходимо избежать возникновения исключения.</span><span class="sxs-lookup"><span data-stu-id="8a06f-124">You can also use the [TryCast Operator](../../../language-reference/operators/trycast-operator.md) keyword if you want to avoid throwing an exception.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a06f-125">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8a06f-125">See also</span></span>

- [<span data-ttu-id="8a06f-126">Массивы</span><span class="sxs-lookup"><span data-stu-id="8a06f-126">Arrays</span></span>](index.md)
- [<span data-ttu-id="8a06f-127">Устранение неполадок, связанных с массивами</span><span class="sxs-lookup"><span data-stu-id="8a06f-127">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="8a06f-128">Оператор Enum</span><span class="sxs-lookup"><span data-stu-id="8a06f-128">Enum Statement</span></span>](../../../language-reference/statements/enum-statement.md)
- [<span data-ttu-id="8a06f-129">Преобразования массивов</span><span class="sxs-lookup"><span data-stu-id="8a06f-129">Array Conversions</span></span>](../data-types/array-conversions.md)
