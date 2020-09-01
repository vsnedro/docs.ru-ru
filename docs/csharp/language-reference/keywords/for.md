---
description: Оператор for. Справочник по C#
title: Оператор for. Справочник по C#
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: be9ecdc08d54c9cde1c49656a16e0d85a6d7084d
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89126935"
---
# <a name="for-c-reference"></a><span data-ttu-id="82e33-103">for (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="82e33-103">for (C# reference)</span></span>

<span data-ttu-id="82e33-104">Оператор `for` выполняет оператор или блок операторов, пока определенное логическое выражение равно значению `true`.</span><span class="sxs-lookup"><span data-stu-id="82e33-104">The `for` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span>

<span data-ttu-id="82e33-105">В любой момент в блоке операторов `for` вы можете прервать цикл с помощью оператора [break](break.md) или перейти к следующей итерации в цикле с помощью оператора [continue](continue.md).</span><span class="sxs-lookup"><span data-stu-id="82e33-105">At any point within the `for` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="82e33-106">Можно также выйти из цикла `for` с помощью операторов [goto](goto.md), [return](return.md) или [throw](throw.md).</span><span class="sxs-lookup"><span data-stu-id="82e33-106">You can also exit a `for` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="structure-of-the-for-statement"></a><span data-ttu-id="82e33-107">Структура оператора `for`</span><span class="sxs-lookup"><span data-stu-id="82e33-107">Structure of the `for` statement</span></span>

<span data-ttu-id="82e33-108">Оператор `for` определяет разделы *инициализатора*, *условия* и *итератора*:</span><span class="sxs-lookup"><span data-stu-id="82e33-108">The `for` statement defines *initializer*, *condition*, and *iterator* sections:</span></span>

```csharp
for (initializer; condition; iterator)
    body
```

<span data-ttu-id="82e33-109">Все три раздела добавляются по желанию.</span><span class="sxs-lookup"><span data-stu-id="82e33-109">All three sections are optional.</span></span> <span data-ttu-id="82e33-110">Тело цикла является оператором или блоком операторов.</span><span class="sxs-lookup"><span data-stu-id="82e33-110">The body of the loop is either a statement or a block of statements.</span></span>

<span data-ttu-id="82e33-111">В следующем примере показан оператор `for` со всеми определенными разделами:</span><span class="sxs-lookup"><span data-stu-id="82e33-111">The following example shows the `for` statement with all of the sections defined:</span></span>

[!code-csharp-interactive[for loop example](snippets/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a><span data-ttu-id="82e33-112">Раздел *инициализатора*</span><span class="sxs-lookup"><span data-stu-id="82e33-112">The *initializer* section</span></span>

<span data-ttu-id="82e33-113">Операторы в разделе *инициализатора* выполняются только один раз перед входом в цикл.</span><span class="sxs-lookup"><span data-stu-id="82e33-113">The statements in the *initializer* section are executed only once, before entering the loop.</span></span> <span data-ttu-id="82e33-114">Раздел *инициализатора* представляет собой один из следующих объектов:</span><span class="sxs-lookup"><span data-stu-id="82e33-114">The *initializer* section is either of the following:</span></span>

- <span data-ttu-id="82e33-115">Объявление и инициализация локальной переменной цикла, к которой невозможно получить доступ вне цикла.</span><span class="sxs-lookup"><span data-stu-id="82e33-115">The declaration and initialization of a local loop variable, which can't be accessed from outside the loop.</span></span>

- <span data-ttu-id="82e33-116">Ноль или более выражений операторов из следующего списка, разделенные запятыми:</span><span class="sxs-lookup"><span data-stu-id="82e33-116">Zero or more statement expressions from the following list, separated by commas:</span></span>

  - <span data-ttu-id="82e33-117">оператор [присваивания](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="82e33-117">[assignment](../operators/assignment-operator.md) statement</span></span>

  - <span data-ttu-id="82e33-118">вызов метода</span><span class="sxs-lookup"><span data-stu-id="82e33-118">invocation of a method</span></span>

  - <span data-ttu-id="82e33-119">префиксное или постфиксное выражение [приращения](../operators/arithmetic-operators.md#increment-operator-), такое как `++i` или `i++`</span><span class="sxs-lookup"><span data-stu-id="82e33-119">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

  - <span data-ttu-id="82e33-120">префиксное или постфиксное выражение [декремента](../operators/arithmetic-operators.md#decrement-operator---), такое как `--i` или `i--`</span><span class="sxs-lookup"><span data-stu-id="82e33-120">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

  - <span data-ttu-id="82e33-121">создание объекта с помощью оператора [new](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="82e33-121">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

  - <span data-ttu-id="82e33-122">выражение [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="82e33-122">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="82e33-123">Раздел *инициализатора* в приведенном выше примере объявляет и инициализирует локальную переменную цикла `i`:</span><span class="sxs-lookup"><span data-stu-id="82e33-123">The *initializer* section in the example above declares and initializes the local loop variable `i`:</span></span>

```csharp
int i = 0
```

### <a name="the-condition-section"></a><span data-ttu-id="82e33-124">Раздел *условия*</span><span class="sxs-lookup"><span data-stu-id="82e33-124">The *condition* section</span></span>

<span data-ttu-id="82e33-125">Раздел *условия*, если он определен, должен быть логическим выражением.</span><span class="sxs-lookup"><span data-stu-id="82e33-125">The *condition* section, if present, must be a boolean expression.</span></span> <span data-ttu-id="82e33-126">Это выражение оценивается перед каждой итерацией цикла.</span><span class="sxs-lookup"><span data-stu-id="82e33-126">That expression is evaluated before every loop iteration.</span></span> <span data-ttu-id="82e33-127">Если раздел *условия* отсутствует или логическое выражение имеет значение `true`, выполняется следующая итерация цикла. В противном случае выполняется выход из цикла.</span><span class="sxs-lookup"><span data-stu-id="82e33-127">If the *condition* section is not present or the boolean expression evaluates to `true`, the next loop iteration is executed; otherwise, the loop is exited.</span></span>

<span data-ttu-id="82e33-128">Раздел *условия* в приведенном выше примере определяет, завершится ли цикл в зависимости от значения локальной переменной цикла:</span><span class="sxs-lookup"><span data-stu-id="82e33-128">The *condition* section in the example above determines if the loop terminates based on the value of the local loop variable:</span></span>

```csharp
i < 5
```

### <a name="the-iterator-section"></a><span data-ttu-id="82e33-129">Раздел *итератора*</span><span class="sxs-lookup"><span data-stu-id="82e33-129">The *iterator* section</span></span>

<span data-ttu-id="82e33-130">Раздел *итератора* определяет, что происходит после каждой итерации тела цикла.</span><span class="sxs-lookup"><span data-stu-id="82e33-130">The *iterator* section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="82e33-131">Раздел *итератора* содержит ноль или более следующих выражений оператора, разделенных запятыми:</span><span class="sxs-lookup"><span data-stu-id="82e33-131">The *iterator* section contains zero or more of the following statement expressions, separated by commas:</span></span>

- <span data-ttu-id="82e33-132">оператор [присваивания](../operators/assignment-operator.md)</span><span class="sxs-lookup"><span data-stu-id="82e33-132">[assignment](../operators/assignment-operator.md) statement</span></span>

- <span data-ttu-id="82e33-133">вызов метода</span><span class="sxs-lookup"><span data-stu-id="82e33-133">invocation of a method</span></span>

- <span data-ttu-id="82e33-134">префиксное или постфиксное выражение [приращения](../operators/arithmetic-operators.md#increment-operator-), такое как `++i` или `i++`</span><span class="sxs-lookup"><span data-stu-id="82e33-134">prefix or postfix [increment](../operators/arithmetic-operators.md#increment-operator-) expression, such as `++i` or `i++`</span></span>

- <span data-ttu-id="82e33-135">префиксное или постфиксное выражение [декремента](../operators/arithmetic-operators.md#decrement-operator---), такое как `--i` или `i--`</span><span class="sxs-lookup"><span data-stu-id="82e33-135">prefix or postfix [decrement](../operators/arithmetic-operators.md#decrement-operator---) expression, such as `--i` or `i--`</span></span>

- <span data-ttu-id="82e33-136">создание объекта с помощью оператора [new](../operators/new-operator.md)</span><span class="sxs-lookup"><span data-stu-id="82e33-136">creation of an object by using the [new](../operators/new-operator.md) operator</span></span>

- <span data-ttu-id="82e33-137">выражение [await](../operators/await.md)</span><span class="sxs-lookup"><span data-stu-id="82e33-137">[await](../operators/await.md) expression</span></span>

<span data-ttu-id="82e33-138">Раздел *итератора* в приведенном выше примере увеличивает локальную переменную цикла:</span><span class="sxs-lookup"><span data-stu-id="82e33-138">The *iterator* section in the example above increments the local loop variable:</span></span>

```csharp
i++
```

## <a name="examples"></a><span data-ttu-id="82e33-139">Примеры</span><span class="sxs-lookup"><span data-stu-id="82e33-139">Examples</span></span>

<span data-ttu-id="82e33-140">В следующем примере показано несколько менее распространенных вариантов использования разделов оператора `for`: присваивание значения внешней переменной цикла в разделе *инициализатора*, вызов метода в разделах *инициализатора* и *итератора* и изменение значения двух переменных в разделе *итератора*.</span><span class="sxs-lookup"><span data-stu-id="82e33-140">The following example illustrates several less common usages of the `for` statement sections: assigning a value to an external loop variable in the *initializer* section, invoking a method in both the *initializer* and the *iterator* sections, and changing the values of two variables in the *iterator* section.</span></span> <span data-ttu-id="82e33-141">Нажмите **Запустить** для выполнения примера кода.</span><span class="sxs-lookup"><span data-stu-id="82e33-141">Select **Run** to run the example code.</span></span> <span data-ttu-id="82e33-142">После этого можно изменить код и запустить его еще раз.</span><span class="sxs-lookup"><span data-stu-id="82e33-142">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[not typical for loop example](snippets/IterationKeywordsExamples.cs#6)]

<span data-ttu-id="82e33-143">В следующем примере определен бесконечный цикл `for`:</span><span class="sxs-lookup"><span data-stu-id="82e33-143">The following example defines the infinite `for` loop:</span></span>

[!code-csharp[infinite for loop example](snippets/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a><span data-ttu-id="82e33-144">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="82e33-144">C# language specification</span></span>

<span data-ttu-id="82e33-145">Дополнительные сведения см. в разделе [Оператор for](~/_csharplang/spec/statements.md#the-for-statement) в документации [Предварительная спецификация C# 6.0](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="82e33-145">For more information, see [The for statement](~/_csharplang/spec/statements.md#the-for-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="82e33-146">См. также</span><span class="sxs-lookup"><span data-stu-id="82e33-146">See also</span></span>

- [<span data-ttu-id="82e33-147">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="82e33-147">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="82e33-148">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="82e33-148">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="82e33-149">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="82e33-149">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="82e33-150">foreach, in</span><span class="sxs-lookup"><span data-stu-id="82e33-150">foreach, in</span></span>](foreach-in.md)
