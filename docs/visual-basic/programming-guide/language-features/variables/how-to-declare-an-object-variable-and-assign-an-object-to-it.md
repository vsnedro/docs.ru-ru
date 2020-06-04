---
title: Практическое руководство. Объявление объектной переменной и присвоение ей объекта
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: d9a8c1fb30bfa5988d48202e41202e7ede0f5f27
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410507"
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a><span data-ttu-id="b3e92-102">Практическое руководство. Объявление объектной переменной в Visual Basic и присвоение ей объекта</span><span class="sxs-lookup"><span data-stu-id="b3e92-102">How to: Declare an Object Variable and Assign an Object to It in Visual Basic</span></span>

<span data-ttu-id="b3e92-103">Переменная [типа данных Object](../../../language-reference/data-types/object-data-type.md) объявляется путем указания `As Object` в [операторе Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b3e92-103">You declare a variable of the [Object Data Type](../../../language-reference/data-types/object-data-type.md) by specifying `As Object` in a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="b3e92-104">Вы назначаете объект такой переменной, помещая объект после знака равенства ( `=` ) в операторе присваивания или предложении инициализации.</span><span class="sxs-lookup"><span data-stu-id="b3e92-104">You assign an object to such a variable by placing the object after the equal sign (`=`) in an assignment statement or initialization clause.</span></span>

## <a name="example"></a><span data-ttu-id="b3e92-105">Пример</span><span class="sxs-lookup"><span data-stu-id="b3e92-105">Example</span></span>

<span data-ttu-id="b3e92-106">В следующем примере объявляется `Object` переменная и назначается ей текущий экземпляр.</span><span class="sxs-lookup"><span data-stu-id="b3e92-106">The following example declares an `Object` variable and assigns the current instance to it.</span></span>

```vb
Dim thisObject As Object
thisObject = "This is an Object"
```

<span data-ttu-id="b3e92-107">Объявление и присваивание можно объединить, инициализируя переменную как часть ее объявления.</span><span class="sxs-lookup"><span data-stu-id="b3e92-107">You can combine the declaration and assignment by initializing the variable as part of its declaration.</span></span> <span data-ttu-id="b3e92-108">Следующий пример эквивалентен предыдущему примеру.</span><span class="sxs-lookup"><span data-stu-id="b3e92-108">The following example is equivalent to the preceding example.</span></span>

```vb
Dim thisObject As Object= "This is an Object"
```

## <a name="compile-the-code"></a><span data-ttu-id="b3e92-109">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="b3e92-109">Compile the code</span></span>

<span data-ttu-id="b3e92-110">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="b3e92-110">This example requires:</span></span>

- <span data-ttu-id="b3e92-111">ссылка на пространство имен <xref:System>.</span><span class="sxs-lookup"><span data-stu-id="b3e92-111">A reference to the <xref:System> namespace.</span></span>

- <span data-ttu-id="b3e92-112">Класс, структура или модуль, в котором будет размещена `Dim` инструкция.</span><span class="sxs-lookup"><span data-stu-id="b3e92-112">A class, structure, or module in which to put the `Dim` statement.</span></span>

- <span data-ttu-id="b3e92-113">Процедура, в которой следует разместить оператор присваивания.</span><span class="sxs-lookup"><span data-stu-id="b3e92-113">A procedure in which to put the assignment statement.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3e92-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b3e92-114">See also</span></span>

- [<span data-ttu-id="b3e92-115">Объявление переменной</span><span class="sxs-lookup"><span data-stu-id="b3e92-115">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="b3e92-116">Объектные переменные</span><span class="sxs-lookup"><span data-stu-id="b3e92-116">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="b3e92-117">Объявление объектной переменной</span><span class="sxs-lookup"><span data-stu-id="b3e92-117">Object Variable Declaration</span></span>](object-variable-declaration.md)
- [<span data-ttu-id="b3e92-118">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="b3e92-118">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)
- [<span data-ttu-id="b3e92-119">Оператор Dim</span><span class="sxs-lookup"><span data-stu-id="b3e92-119">Dim Statement</span></span>](../../../language-reference/statements/dim-statement.md)
- [<span data-ttu-id="b3e92-120">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="b3e92-120">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="b3e92-121">Оператор Option Strict</span><span class="sxs-lookup"><span data-stu-id="b3e92-121">Option Strict Statement</span></span>](../../../language-reference/statements/option-strict-statement.md)
