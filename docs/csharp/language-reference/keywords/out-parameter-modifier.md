---
description: Справочник по C#. Модификатор параметров out
title: Справочник по C#. Модификатор параметров out
ms.date: 03/19/2020
helpviewer_keywords:
- parameters [C#], out
- out parameters [C#]
ms.openlocfilehash: 23bf841c002f9be5fdd4e8d8da48e68e9f6e5fcc
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122437"
---
# <a name="out-parameter-modifier-c-reference"></a><span data-ttu-id="d9a60-103">Модификатор параметров out (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="d9a60-103">out parameter modifier (C# Reference)</span></span>

<span data-ttu-id="d9a60-104">Ключевое `out` инициирует передачу аргументов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="d9a60-104">The `out` keyword causes arguments to be passed by reference.</span></span> <span data-ttu-id="d9a60-105">В результате этот формальный параметр становится псевдонимом для аргумента, который должен представлять собой переменную.</span><span class="sxs-lookup"><span data-stu-id="d9a60-105">It makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="d9a60-106">Другими словами, любая операция в параметре осуществляется с аргументом.</span><span class="sxs-lookup"><span data-stu-id="d9a60-106">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="d9a60-107">Оно схоже с ключевым словом [ref](ref.md) за исключением того, что при использовании `ref` перед передачей переменную необходимо инициализировать.</span><span class="sxs-lookup"><span data-stu-id="d9a60-107">It is like the [ref](ref.md) keyword, except that `ref` requires that the variable be initialized before it is passed.</span></span> <span data-ttu-id="d9a60-108">Оно также похоже на ключевое слово [in](in-parameter-modifier.md) за исключением того, что `in` не позволяет вызываемому методу изменять значение аргумента.</span><span class="sxs-lookup"><span data-stu-id="d9a60-108">It is also like the [in](in-parameter-modifier.md) keyword, except that `in` does not allow the called method to modify the argument value.</span></span> <span data-ttu-id="d9a60-109">Для применения параметра `out` определение метода и метод вызова должны явно использовать ключевое слово `out`.</span><span class="sxs-lookup"><span data-stu-id="d9a60-109">To use an `out` parameter, both the method definition and the calling method must explicitly use the `out` keyword.</span></span> <span data-ttu-id="d9a60-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="d9a60-110">For example:</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#1)]  

> [!NOTE]
> <span data-ttu-id="d9a60-111">Ключевое слово `out` также можно использовать с параметром универсального типа для указания на то, что тип параметра является ковариантным.</span><span class="sxs-lookup"><span data-stu-id="d9a60-111">The `out` keyword can also be used with a generic type parameter to specify that the type parameter is covariant.</span></span> <span data-ttu-id="d9a60-112">Дополнительные сведения об использовании ключевого слова `out` в этом контексте см. в разделе [out (универсальный модификатор)](out-generic-modifier.md).</span><span class="sxs-lookup"><span data-stu-id="d9a60-112">For more information on the use of the `out` keyword in this context, see [out (Generic Modifier)](out-generic-modifier.md).</span></span>
  
<span data-ttu-id="d9a60-113">Переменные, передаваемые в качестве аргументов `out`, не требуется инициализировать перед передачей в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="d9a60-113">Variables passed as `out` arguments do not have to be initialized before being passed in a method call.</span></span> <span data-ttu-id="d9a60-114">Но перед передачей управления из вызванного метода он должен присвоить значение.</span><span class="sxs-lookup"><span data-stu-id="d9a60-114">However, the called method is required to assign a value before the method returns.</span></span>  
  
<span data-ttu-id="d9a60-115">Ключевые слова `in`, `ref` и `out` не считаются частью сигнатуры метода для разрешения перегрузки.</span><span class="sxs-lookup"><span data-stu-id="d9a60-115">The `in`, `ref`, and `out` keywords are not considered part of the method signature for the purpose of overload resolution.</span></span> <span data-ttu-id="d9a60-116">Таким образом, методы не могут быть перегружены, если единственное различие состоит в том, что один метод принимает аргумент `ref` или `in`, а другой — `out`.</span><span class="sxs-lookup"><span data-stu-id="d9a60-116">Therefore, methods cannot be overloaded if the only difference is that one method takes a `ref` or `in` argument and the other takes an `out` argument.</span></span> <span data-ttu-id="d9a60-117">Следующий код, например, компилироваться не будет.</span><span class="sxs-lookup"><span data-stu-id="d9a60-117">The following code, for example, will not compile:</span></span>  
  
```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```
  
<span data-ttu-id="d9a60-118">Перегрузка допустима, если один метод принимает аргумент `ref`, `in` или `out`, а другой не использует ни один из этих модификаторов, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="d9a60-118">Overloading is legal, however, if one method takes a `ref`, `in`, or `out` argument and the other has none of those modifiers, like this:</span></span>  
  
[!code-csharp[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#2)]  

<span data-ttu-id="d9a60-119">Компилятор выбирает наиболее подходящую перегрузку, сравнивая модификаторы параметров в месте вызова с модификаторами параметров в вызове метода.</span><span class="sxs-lookup"><span data-stu-id="d9a60-119">The compiler chooses the best overload by matching the parameter modifiers at the call site to the parameter modifiers used in the method call.</span></span>

<span data-ttu-id="d9a60-120">Свойства не являются переменными и поэтому не могут быть переданы как параметры `out`.</span><span class="sxs-lookup"><span data-stu-id="d9a60-120">Properties are not variables and therefore cannot be passed as `out` parameters.</span></span>
  
<span data-ttu-id="d9a60-121">Ключевые слова `in`, `ref` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="d9a60-121">You can't use the `in`, `ref`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="d9a60-122">Асинхронные методы, которые определяются с помощью модификатора [async](./async.md).</span><span class="sxs-lookup"><span data-stu-id="d9a60-122">Async methods, which you define by using the [async](./async.md) modifier.</span></span>  
  
- <span data-ttu-id="d9a60-123">Методы итератора, которые включают оператор [yield return](./yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="d9a60-123">Iterator methods, which include a [yield return](./yield.md) or `yield break` statement.</span></span>  

<span data-ttu-id="d9a60-124">Кроме того, [методы расширения](../../programming-guide/classes-and-structs/extension-methods.md) имеют следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="d9a60-124">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="d9a60-125">Ключевое слово `out` нельзя использовать в первом аргументе метода расширения.</span><span class="sxs-lookup"><span data-stu-id="d9a60-125">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="d9a60-126">Ключевое слово `ref` нельзя использовать в первом аргументе метода расширения, если аргумент не является структурой, или если универсальный тип не ограничен структурой.</span><span class="sxs-lookup"><span data-stu-id="d9a60-126">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="d9a60-127">Ключевое слово `in` нельзя использовать, если только первый аргумент не является структурой.</span><span class="sxs-lookup"><span data-stu-id="d9a60-127">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="d9a60-128">Ключевое слово `in` нельзя использовать ни для одного универсального типа, даже если оно ограничено структурой.</span><span class="sxs-lookup"><span data-stu-id="d9a60-128">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="declaring-out-parameters"></a><span data-ttu-id="d9a60-129">Объявление параметров `out`</span><span class="sxs-lookup"><span data-stu-id="d9a60-129">Declaring `out` parameters</span></span>

<span data-ttu-id="d9a60-130">Объявление метода с аргументами `out` — стандартное решение для возвращения нескольких значений.</span><span class="sxs-lookup"><span data-stu-id="d9a60-130">Declaring a method with `out` arguments is a classic workaround to return multiple values.</span></span> <span data-ttu-id="d9a60-131">Начиная с версии C# 7.0, вы можете использовать [кортежи значений](../builtin-types/value-tuples.md) для таких сценариев.</span><span class="sxs-lookup"><span data-stu-id="d9a60-131">Beginning with C# 7.0, consider [value tuples](../builtin-types/value-tuples.md) for similar scenarios.</span></span> <span data-ttu-id="d9a60-132">В следующем примере используется `out` для возвращения трех переменных с помощью вызова одного метода.</span><span class="sxs-lookup"><span data-stu-id="d9a60-132">The following example uses `out` to return three variables with a single method call.</span></span> <span data-ttu-id="d9a60-133">Третьему аргументу присвоено значение NULL.</span><span class="sxs-lookup"><span data-stu-id="d9a60-133">The third argument is assigned to null.</span></span> <span data-ttu-id="d9a60-134">Это позволяет методам возвращать значения по желанию.</span><span class="sxs-lookup"><span data-stu-id="d9a60-134">This enables methods to return values optionally.</span></span>  
  
[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#3)]  

## <a name="calling-a-method-with-an-out-argument"></a><span data-ttu-id="d9a60-135">Вызов метода с аргументом `out`</span><span class="sxs-lookup"><span data-stu-id="d9a60-135">Calling a method with an `out` argument</span></span>

<span data-ttu-id="d9a60-136">В C# 6 и более ранних версиях необходимо было объявлять переменную в отдельном операторе, прежде чем передавать ее как аргумент `out`.</span><span class="sxs-lookup"><span data-stu-id="d9a60-136">In C# 6 and earlier, you must declare a variable in a separate statement before you pass it as an `out` argument.</span></span> <span data-ttu-id="d9a60-137">В следующем примере переменная `number` объявляется перед передачей в метод [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)), который пытается преобразовать строку в число.</span><span class="sxs-lookup"><span data-stu-id="d9a60-137">The following example declares a variable named `number` before it is passed to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method, which attempts to convert a string to a number.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#4)]  

<span data-ttu-id="d9a60-138">Начиная с C# версии 7.0 переменную `out` можно объявлять в списке аргументов вызова метода, а не отдельно.</span><span class="sxs-lookup"><span data-stu-id="d9a60-138">Starting with C# 7.0, you can declare the `out` variable in the argument list of the method call, rather than in a separate variable declaration.</span></span> <span data-ttu-id="d9a60-139">Это делает код более кратким и удобным для восприятия, а также предотвращает непреднамеренное присвоение значения переменной перед вызовом метода.</span><span class="sxs-lookup"><span data-stu-id="d9a60-139">This produces more compact, readable code, and also prevents you from inadvertently assigning a value to the variable before the method call.</span></span> <span data-ttu-id="d9a60-140">Следующий пример аналогичен предыдущему за тем исключением, что переменная `number` объявляется в вызове метода [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)).</span><span class="sxs-lookup"><span data-stu-id="d9a60-140">The following example is like the previous example, except that it defines the `number` variable in the call to the [Int32.TryParse](xref:System.Int32.TryParse(System.String,System.Int32@)) method.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#5)]  

<span data-ttu-id="d9a60-141">В предыдущем примере переменная `number` строго типизирована как `int`.</span><span class="sxs-lookup"><span data-stu-id="d9a60-141">In the previous example, the `number` variable is strongly typed as an `int`.</span></span> <span data-ttu-id="d9a60-142">Вы также можете объявить неявно типизированную локальную переменную, как в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="d9a60-142">You can also declare an implicitly typed local variable, as the following example does.</span></span>

[!code-csharp-interactive[cs-out-keyword](../../../../samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/OutParameterModifier.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="d9a60-143">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="d9a60-143">C# Language Specification</span></span>  
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d9a60-144">См. также</span><span class="sxs-lookup"><span data-stu-id="d9a60-144">See also</span></span>

- [<span data-ttu-id="d9a60-145">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="d9a60-145">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="d9a60-146">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="d9a60-146">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="d9a60-147">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="d9a60-147">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="d9a60-148">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="d9a60-148">Method Parameters</span></span>](./method-parameters.md)
