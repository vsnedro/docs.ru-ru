---
title: Практическое руководство. Создание новой переменной
ms.date: 07/20/2015
helpviewer_keywords:
- Dim statement [Visual Basic]
- variables [Visual Basic], creating
ms.assetid: 35300be3-77b0-4bef-a156-034d3cdedde0
ms.openlocfilehash: 501c8f3aff4c5b204d231bdc26213e13d125a7cf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410533"
---
# <a name="how-to-create-a-new-variable-visual-basic"></a><span data-ttu-id="b1a5c-102">Практическое руководство. Создание новой переменной (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b1a5c-102">How to: Create a New Variable (Visual Basic)</span></span>

<span data-ttu-id="b1a5c-103">Переменная создается с помощью [оператора Dim](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1a5c-103">You create a variable with a [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span>

### <a name="to-create-a-new-variable"></a><span data-ttu-id="b1a5c-104">Создание новой переменной</span><span class="sxs-lookup"><span data-stu-id="b1a5c-104">To create a new variable</span></span>

1. <span data-ttu-id="b1a5c-105">Объявите переменную в `Dim` операторе.</span><span class="sxs-lookup"><span data-stu-id="b1a5c-105">Declare the variable in a `Dim` statement.</span></span>

    ```vb
    Dim newCustomer
    ```

2. <span data-ttu-id="b1a5c-106">Включите спецификации для характеристик переменной, например [Private](../../../language-reference/modifiers/private.md), [static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md)или [WithEvents](../../../language-reference/modifiers/withevents.md).</span><span class="sxs-lookup"><span data-stu-id="b1a5c-106">Include specifications for the variable's characteristics, such as [Private](../../../language-reference/modifiers/private.md), [Static](../../../language-reference/modifiers/static.md), [Shadows](../../../language-reference/modifiers/shadows.md), or [WithEvents](../../../language-reference/modifiers/withevents.md).</span></span> <span data-ttu-id="b1a5c-107">Дополнительные сведения см. в разделе [Характеристики объявленных элементов](../declared-elements/declared-element-characteristics.md).</span><span class="sxs-lookup"><span data-stu-id="b1a5c-107">For more information, see [Declared Element Characteristics](../declared-elements/declared-element-characteristics.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

    <span data-ttu-id="b1a5c-108">`Dim`Ключевое слово не требуется, если в объявлении используются другие ключевые слова.</span><span class="sxs-lookup"><span data-stu-id="b1a5c-108">You do not need the `Dim` keyword if you use other keywords in the declaration.</span></span>

3. <span data-ttu-id="b1a5c-109">Используйте спецификации с именем переменной, которое должно соответствовать правилам и соглашениям Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="b1a5c-109">Follow the specifications with the variable's name, which must follow Visual Basic rules and conventions.</span></span> <span data-ttu-id="b1a5c-110">Дополнительные сведения см. в разделе [Имена объявленных элементов](../declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="b1a5c-110">For more information, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>

    ```vb
    Public Static newCustomer
    ```

4. <span data-ttu-id="b1a5c-111">Чтобы указать тип данных переменной, используйте имя с предложением [as](../../../language-reference/statements/as-clause.md) .</span><span class="sxs-lookup"><span data-stu-id="b1a5c-111">Follow the name with the [As](../../../language-reference/statements/as-clause.md) clause to specify the variable's data type.</span></span>

    ```vb
    Public Static newCustomer As Customer
    ```

    <span data-ttu-id="b1a5c-112">Если тип данных не указан, используется значение по умолчанию: `Object` .</span><span class="sxs-lookup"><span data-stu-id="b1a5c-112">If you do not specify the data type, it uses the default: `Object`.</span></span>

5. <span data-ttu-id="b1a5c-113">Следуйте `As` предложению со знаком равенства ( `=` ) и выполните знак равенства с начальным значением переменной.</span><span class="sxs-lookup"><span data-stu-id="b1a5c-113">Follow the `As` clause with an equal sign (`=`) and follow the equal sign with the variable's initial value.</span></span>

    <span data-ttu-id="b1a5c-114">Visual Basic назначает указанное значение переменной при каждом выполнении `Dim` инструкции.</span><span class="sxs-lookup"><span data-stu-id="b1a5c-114">Visual Basic assigns the specified value to the variable every time it runs the `Dim` statement.</span></span> <span data-ttu-id="b1a5c-115">Если не указать начальное значение, Visual Basic присваивает начальное значение по умолчанию для типа данных переменной при первом входе в код, содержащий `Dim` инструкцию.</span><span class="sxs-lookup"><span data-stu-id="b1a5c-115">If you do not specify an initial value, Visual Basic assigns the default initial value for the variable's data type when it first enters the code that contains the `Dim` statement.</span></span>

    <span data-ttu-id="b1a5c-116">Если переменная является ссылочным типом, можно создать экземпляр его класса, включив в предложение ключевое слово [New operator](../../../language-reference/operators/new-operator.md) `As` .</span><span class="sxs-lookup"><span data-stu-id="b1a5c-116">If the variable is a reference type, you can create an instance of its class by including the [New Operator](../../../language-reference/operators/new-operator.md) keyword in the `As` clause.</span></span> <span data-ttu-id="b1a5c-117">Если не используется `New` , начальное значение переменной равно [Nothing](../../../language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="b1a5c-117">If you do not use `New`, the initial value of the variable is [Nothing](../../../language-reference/nothing.md).</span></span>

    ```vb
    Public Static newCustomer As New Customer
    ```

## <a name="see-also"></a><span data-ttu-id="b1a5c-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b1a5c-118">See also</span></span>

- [<span data-ttu-id="b1a5c-119">Переменные</span><span class="sxs-lookup"><span data-stu-id="b1a5c-119">Variables</span></span>](index.md)
- [<span data-ttu-id="b1a5c-120">Объявление переменной</span><span class="sxs-lookup"><span data-stu-id="b1a5c-120">Variable Declaration</span></span>](variable-declaration.md)
- [<span data-ttu-id="b1a5c-121">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="b1a5c-121">Declared Element Names</span></span>](../declared-elements/declared-element-names.md)
- [<span data-ttu-id="b1a5c-122">Характеристики объявленных элементов</span><span class="sxs-lookup"><span data-stu-id="b1a5c-122">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="b1a5c-123">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="b1a5c-123">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
- [<span data-ttu-id="b1a5c-124">Операторы</span><span class="sxs-lookup"><span data-stu-id="b1a5c-124">Statements</span></span>](../../../language-reference/statements/index.md)
- [<span data-ttu-id="b1a5c-125">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="b1a5c-125">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="b1a5c-126">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="b1a5c-126">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
