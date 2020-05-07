---
title: '!  — оператор (допускающий значение NULL) — справочник по C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 2a8db2882968dbcbe6a8868ab6fe1c128c94a41f
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624882"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="12557-103">!</span><span class="sxs-lookup"><span data-stu-id="12557-103">!</span></span> <span data-ttu-id="12557-104"> — оператор (допускающий значение NULL) (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="12557-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="12557-105">Унарный постфиксный оператор `!`, доступный в C# 8.0 и более поздних версиях, допускает значение NULL.</span><span class="sxs-lookup"><span data-stu-id="12557-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="12557-106">При включенном [контексте аннотаций с поддержкой значения NULL](../../nullable-references.md#nullable-annotation-context) можно использовать оператор, допускающий значение NULL, чтобы объявить, что выражение `x` для ссылочного типа, допускающего значение NULL, не равно `null`: `x!`.</span><span class="sxs-lookup"><span data-stu-id="12557-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="12557-107">Унарный префиксный оператор `!` является [оператором логического отрицания](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="12557-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="12557-108">Оператор, допускающий NULL, ни на что не влияет во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="12557-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="12557-109">Он влияет только на статический анализ потока компилятора путем изменения состояния NULL выражения.</span><span class="sxs-lookup"><span data-stu-id="12557-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="12557-110">Во время выполнения выражение `x!` сравнивается с результатом базового выражения `x`.</span><span class="sxs-lookup"><span data-stu-id="12557-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

> [!NOTE]
> <span data-ttu-id="12557-111">В C# 8 оператор, допускающий значение NULL, завершает список предыдущих [условных операций со значением NULL](member-access-operators.md#null-conditional-operators--and-).</span><span class="sxs-lookup"><span data-stu-id="12557-111">In C# 8, the null-forgiving operator terminates the list of preceding [null-conditional](member-access-operators.md#null-conditional-operators--and-) operations.</span></span> <span data-ttu-id="12557-112">Например, выражение `x?.y!.z` анализируется как `(x?.y)!.z`.</span><span class="sxs-lookup"><span data-stu-id="12557-112">For example, the expression `x?.y!.z` is parsed as `(x?.y)!.z`.</span></span> <span data-ttu-id="12557-113">Из-за этой интерпретации `z` вычисляется, даже если `x` — `null`, что может привести к <xref:System.NullReferenceException>.</span><span class="sxs-lookup"><span data-stu-id="12557-113">Due to this interpretation, `z` is evaluated even if `x` is `null`, which may result in a <xref:System.NullReferenceException>.</span></span>

<span data-ttu-id="12557-114">Дополнительные сведения о ссылочных типах, допускающих значения NULL, см. в разделе [Ссылочные типы, допускающие значение NULL](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="12557-114">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="12557-115">Примеры</span><span class="sxs-lookup"><span data-stu-id="12557-115">Examples</span></span>

<span data-ttu-id="12557-116">Один из вариантов использования оператора, допускающего значение NULL, — тестирование логики проверки аргументов.</span><span class="sxs-lookup"><span data-stu-id="12557-116">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="12557-117">Например, рассмотрим следующий класс.</span><span class="sxs-lookup"><span data-stu-id="12557-117">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="12557-118">С помощью [платформы тестирования MSTest](../../../core/testing/unit-testing-with-mstest.md) можно создать следующий тест для логики проверки в конструкторе:</span><span class="sxs-lookup"><span data-stu-id="12557-118">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="12557-119">Без оператора, допускающего значение NULL, компилятор создает следующее предупреждение для предыдущего кода: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="12557-119">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="12557-120">Используя оператор, допускающий значение NULL, вы сообщаете компилятору, что передача `null` ожидается и что о ней не нужно предупреждать.</span><span class="sxs-lookup"><span data-stu-id="12557-120">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="12557-121">Можно также использовать оператор, допускающий значение NULL, если вы точно знаете, что выражение не может быть `null`, но компилятор не распознает это.</span><span class="sxs-lookup"><span data-stu-id="12557-121">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="12557-122">В следующем примере, если метод `IsValid` возвращает `true`, его аргумент не является `null`, и вы можете безопасно отменить его ссылку:</span><span class="sxs-lookup"><span data-stu-id="12557-122">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="12557-123">Без оператора, допускающего значение NULL, компилятор создает следующее предупреждение для кода `p.Name`: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="12557-123">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="12557-124">Если вы можете изменить метод `IsValid`, можно использовать атрибут [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute), чтобы сообщить компилятору, что аргумент метода `IsValid` не может быть `null`, когда метод возвращает `true`:</span><span class="sxs-lookup"><span data-stu-id="12557-124">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="12557-125">В предыдущем примере не нужно использовать оператор, допускающий значение NULL, поскольку компилятор содержит достаточно информации, чтобы определить, что `p` не может быть `null` внутри `if`.</span><span class="sxs-lookup"><span data-stu-id="12557-125">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="12557-126">См. сведения об атрибутах, позволяющих указать дополнительную информацию о состоянии NULL для переменной, в руководстве по [включению в API атрибутов для определения ожидаемых значений NULL](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="12557-126">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="12557-127">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="12557-127">C# language specification</span></span>

<span data-ttu-id="12557-128">См. сведения об [операторе, допускающем значение NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator), в [черновике спецификации по ссылочным типам допускающим значение NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="12557-128">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="12557-129">См. также</span><span class="sxs-lookup"><span data-stu-id="12557-129">See also</span></span>

- [<span data-ttu-id="12557-130">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="12557-130">C# reference</span></span>](../index.md)
- [<span data-ttu-id="12557-131">Операторы в C#</span><span class="sxs-lookup"><span data-stu-id="12557-131">C# operators</span></span>](index.md)
- [<span data-ttu-id="12557-132">Учебник. Разработка с использованием ссылочных типов, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="12557-132">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
