---
description: Справочник по C#. Ключевое слово ref
title: Справочник по C#. Ключевое слово ref
ms.date: 04/21/2020
f1_keywords:
- ref_CSharpKeyword
- ref
helpviewer_keywords:
- parameters [C#], ref
- ref keyword [C#]
ms.openlocfilehash: 58a4ce30e11ca023b50e5e53b1f1554a30d44390
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137088"
---
# <a name="ref-c-reference"></a><span data-ttu-id="dc0ea-103">ref (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="dc0ea-103">ref (C# Reference)</span></span>

<span data-ttu-id="dc0ea-104">Ключевое слово `ref` указывает на значение, переданное по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-104">The `ref` keyword indicates a value that is passed by reference.</span></span> <span data-ttu-id="dc0ea-105">Оно используется в четырех разных контекстах:</span><span class="sxs-lookup"><span data-stu-id="dc0ea-105">It is used in four different contexts:</span></span>

- <span data-ttu-id="dc0ea-106">В сигнатуре и вызове метода для передачи аргумента в метод по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-106">In a method signature and in a method call, to pass an argument to a method by reference.</span></span> <span data-ttu-id="dc0ea-107">Дополнительные сведения см. в статье о [передаче аргументов по ссылке](#passing-an-argument-by-reference).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-107">For more information, see [Passing an argument by reference](#passing-an-argument-by-reference).</span></span>
- <span data-ttu-id="dc0ea-108">В сигнатуре метода для возврата значения вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-108">In a method signature, to return a value to the caller by reference.</span></span> <span data-ttu-id="dc0ea-109">Дополнительные сведения см. в разделе [Значения, возвращаемые по ссылке](#reference-return-values).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-109">For more information, see [Reference return values](#reference-return-values).</span></span>
- <span data-ttu-id="dc0ea-110">В теле элемента для указания на то, что возвращаемые ссылочные значения хранятся локально в виде ссылки, которая может быть изменена вызывающим объектом, или, в общем случае, что локальная переменная обращается к другому значению по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-110">In a member body, to indicate that a reference return value is stored locally as a reference that the caller intends to modify or, in general, a local variable accesses another value by reference.</span></span> <span data-ttu-id="dc0ea-111">Дополнительные сведения см. в статье о [ссылочных локальных переменных](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-111">For more information, see [Ref locals](#ref-locals).</span></span>
- <span data-ttu-id="dc0ea-112">В объявлении `struct`, чтобы объявить `ref struct` или `readonly ref struct`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-112">In a `struct` declaration to declare a `ref struct` or a `readonly ref struct`.</span></span> <span data-ttu-id="dc0ea-113">Дополнительные сведения см. в описании [структуры `ref`](../builtin-types/struct.md#ref-struct) в статье [Типы структур](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-113">For more information, see the [`ref` struct](../builtin-types/struct.md#ref-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>

## <a name="passing-an-argument-by-reference"></a><span data-ttu-id="dc0ea-114">Передача аргументов по ссылке</span><span class="sxs-lookup"><span data-stu-id="dc0ea-114">Passing an argument by reference</span></span>

<span data-ttu-id="dc0ea-115">При использовании в списке параметров метода ключевое слово `ref` указывает на то, что аргумент передается по ссылке, а не по значению.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-115">When used in a method's parameter list, the `ref` keyword indicates that an argument is passed by reference, not by value.</span></span> <span data-ttu-id="dc0ea-116">Ключевое слово `ref` позволяет превратить этот формальный параметр в псевдоним для аргумента, который должен представлять собой переменную.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-116">The `ref` keyword makes the formal parameter an alias for the argument, which must be a variable.</span></span> <span data-ttu-id="dc0ea-117">Другими словами, любая операция в параметре осуществляется с аргументом.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-117">In other words, any operation on the parameter is made on the argument.</span></span> <span data-ttu-id="dc0ea-118">Например, если вызывающий объект передает выражение локальной переменной или выражение доступа к элементу массива и вызванный метод заменяет объект, на который ссылается параметр ref, то после возврата метода локальная переменная или элемент массива взывающего объекта будет ссылаться на новый объект.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-118">For example, if the caller passes a local variable expression or an array element access expression, and the called method replaces the object to which the ref parameter refers, then the caller's local variable or the array element now refers to the new object when the method returns.</span></span>

> [!NOTE]
> <span data-ttu-id="dc0ea-119">Не следует путать понятие передачи по ссылке с понятием ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-119">Do not confuse the concept of passing by reference with the concept of reference types.</span></span> <span data-ttu-id="dc0ea-120">Эти два понятия не совпадают.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-120">The two concepts are not the same.</span></span> <span data-ttu-id="dc0ea-121">Параметр метода может быть изменен с помощью `ref` независимо от того, принадлежит ли он к типу значения или ссылочному типу.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-121">A method parameter can be modified by `ref` regardless of whether it is a value type or a reference type.</span></span> <span data-ttu-id="dc0ea-122">При передаче по ссылке упаковка-преобразование типа значения не производится.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-122">There is no boxing of a value type when it is passed by reference.</span></span>  

<span data-ttu-id="dc0ea-123">Для использования параметра `ref` и при определении метода, и при вызове метода следует явно использовать ключевое слово `ref`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-123">To use a `ref` parameter, both the method definition and the calling method must explicitly use the `ref` keyword, as shown in the following example.</span></span>  

[!code-csharp-interactive[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#1)]

<span data-ttu-id="dc0ea-124">Аргумент, передаваемый в параметр `ref` или `in`, нужно инициализировать перед передачей.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-124">An argument that is passed to a `ref` or `in` parameter must be initialized before it is passed.</span></span> <span data-ttu-id="dc0ea-125">В этом заключается отличие от параметров [out](out-parameter-modifier.md), аргументы которых не требуют явной инициализации перед передачей.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-125">This differs from [out](out-parameter-modifier.md) parameters, whose arguments do not have to be explicitly initialized before they are passed.</span></span>

<span data-ttu-id="dc0ea-126">Члены класса не могут иметь сигнатуры, отличающихся только `ref`, `in` или `out`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-126">Members of a class can't have signatures that differ only by `ref`, `in`, or `out`.</span></span> <span data-ttu-id="dc0ea-127">Если единственное различие между двумя членами типа состоит в том, что один из них имеет параметр `ref`, а второй — параметр `out` или `in`, возникает ошибка компилятора.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-127">A compiler error occurs if the only difference between two members of a type is that one of them has a `ref` parameter and the other has an `out`, or `in` parameter.</span></span> <span data-ttu-id="dc0ea-128">Например, следующий код не будет компилироваться.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-128">The following code, for example, doesn't compile.</span></span>  

```csharp
class CS0663_Example
{
    // Compiler error CS0663: "Cannot define overloaded
    // methods that differ only on ref and out".
    public void SampleMethod(out int i) { }
    public void SampleMethod(ref int i) { }
}
```

<span data-ttu-id="dc0ea-129">Но методы можно перегружать, если один метод имеет параметр `ref`, `in` или `out`, а другой — параметр по значению, как показано в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-129">However, methods can be overloaded when one method has a `ref`, `in`, or `out` parameter and the other has a value parameter, as shown in the following example.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#2)]
  
 <span data-ttu-id="dc0ea-130">В других ситуациях, требующих соответствия сигнатур, таких как скрытие или переопределение, `in`, `ref` и `out` являются частью сигнатуры и не соответствуют друг другу.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-130">In other situations that require signature matching, such as hiding or overriding, `in`, `ref`, and `out` are part of the signature and don't match each other.</span></span>  
  
 <span data-ttu-id="dc0ea-131">Свойства не являются переменными.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-131">Properties are not variables.</span></span> <span data-ttu-id="dc0ea-132">Они являются методами и не могут быть переданы в параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-132">They are methods, and cannot be passed to `ref` parameters.</span></span>  
  
 <span data-ttu-id="dc0ea-133">Ключевые слова `ref`, `in` и `out` запрещено использовать для следующих типов методов.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-133">You can't use the `ref`, `in`, and `out` keywords for the following kinds of methods:</span></span>  
  
- <span data-ttu-id="dc0ea-134">Асинхронные методы, которые определяются с помощью модификатора [async](async.md).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-134">Async methods, which you define by using the [async](async.md) modifier.</span></span>  
- <span data-ttu-id="dc0ea-135">Методы итератора, которые включают оператор [yield return](yield.md) или `yield break`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-135">Iterator methods, which include a [yield return](yield.md) or `yield break` statement.</span></span>

<span data-ttu-id="dc0ea-136">Кроме того, [методы расширения](../../programming-guide/classes-and-structs/extension-methods.md) имеют следующие ограничения:</span><span class="sxs-lookup"><span data-stu-id="dc0ea-136">In addition, [extension methods](../../programming-guide/classes-and-structs/extension-methods.md) have the following restrictions:</span></span>

- <span data-ttu-id="dc0ea-137">Ключевое слово `out` нельзя использовать в первом аргументе метода расширения.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-137">The `out` keyword cannot be used on the first argument of an extension method.</span></span>
- <span data-ttu-id="dc0ea-138">Ключевое слово `ref` нельзя использовать в первом аргументе метода расширения, если аргумент не является структурой, или если универсальный тип не ограничен структурой.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-138">The `ref` keyword cannot be used on the first argument of an extension method when the argument is not a struct, or a generic type not constrained to be a struct.</span></span>
- <span data-ttu-id="dc0ea-139">Ключевое слово `in` нельзя использовать, если только первый аргумент не является структурой.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-139">The `in` keyword cannot be used unless the first argument is a struct.</span></span> <span data-ttu-id="dc0ea-140">Ключевое слово `in` нельзя использовать ни для одного универсального типа, даже если оно ограничено структурой.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-140">The `in` keyword cannot be used on any generic type, even when constrained to be a struct.</span></span>

## <a name="passing-an-argument-by-reference-an-example"></a><span data-ttu-id="dc0ea-141">Передача аргументов по ссылке. Пример</span><span class="sxs-lookup"><span data-stu-id="dc0ea-141">Passing an argument by reference: An example</span></span>

<span data-ttu-id="dc0ea-142">В предыдущих примерах типы значений передаются по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-142">The previous examples pass value types by reference.</span></span> <span data-ttu-id="dc0ea-143">Также можно использовать ключевое слово `ref` для передачи ссылочных типов по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-143">You can also use the `ref` keyword to pass reference types by reference.</span></span> <span data-ttu-id="dc0ea-144">Передача ссылочного типа по ссылке позволяет вызываемому методу заменять объект, на который указывает ссылочный параметр в вызывающем объекте.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-144">Passing a reference type by reference enables the called method to replace the object to which the reference parameter refers in the caller.</span></span> <span data-ttu-id="dc0ea-145">Место хранения объекта передается методу в качестве значения ссылочного параметра.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-145">The storage location of the object is passed to the method as the value of the reference parameter.</span></span> <span data-ttu-id="dc0ea-146">Если изменить место хранения параметра (с указанием на новый объект), необходимо изменить место хранения, на который ссылается вызывающий объект.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-146">If you change the value in the storage location of the parameter (to point to a new object), you also change the storage location to which the caller refers.</span></span> <span data-ttu-id="dc0ea-147">В следующем примере экземпляр ссылочного типа передается как параметр `ref`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-147">The following example passes an instance of a reference type as a `ref` parameter.</span></span>
  
[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#3)]

<span data-ttu-id="dc0ea-148">Дополнительные сведения о передаче ссылочных типов по значению и по ссылке см. в разделе [Передача параметров ссылочного типа](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-148">For more information about how to pass reference types by value and by reference, see [Passing Reference-Type Parameters](../../programming-guide/classes-and-structs/passing-reference-type-parameters.md).</span></span>
  
## <a name="reference-return-values"></a><span data-ttu-id="dc0ea-149">Возвращаемые ссылочные значения</span><span class="sxs-lookup"><span data-stu-id="dc0ea-149">Reference return values</span></span>

<span data-ttu-id="dc0ea-150">Возвращаемые ссылочные значения — это значения, которые метод возвращает вызывающему объекту по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-150">Reference return values (or ref returns) are values that a method returns by reference to the caller.</span></span> <span data-ttu-id="dc0ea-151">Это значит, что вызывающий объект может изменять значение, возвращаемое методом, и это изменение будет отражаться в состоянии объекта в вызывающем методе.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-151">That is, the caller can modify the value returned by a method, and that change is reflected in the state of the object in the calling method.</span></span>

<span data-ttu-id="dc0ea-152">Возвращаемое ссылочное значение определяется с помощью ключевого слова `ref`:</span><span class="sxs-lookup"><span data-stu-id="dc0ea-152">A reference return value is defined by using the `ref` keyword:</span></span>

- <span data-ttu-id="dc0ea-153">В сигнатуре метода.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-153">In the method signature.</span></span> <span data-ttu-id="dc0ea-154">Например, следующая сигнатура указывает, что метод `GetCurrentPrice` возвращает значение <xref:System.Decimal> по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-154">For example, the following method signature indicates that the `GetCurrentPrice` method returns a <xref:System.Decimal> value by reference.</span></span>

```csharp
public ref decimal GetCurrentPrice()
```

- <span data-ttu-id="dc0ea-155">Между токеном `return` и переменной, возвращенной в инструкции `return` в методе.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-155">Between the `return` token and the variable returned in a `return` statement in the method.</span></span> <span data-ttu-id="dc0ea-156">Пример:</span><span class="sxs-lookup"><span data-stu-id="dc0ea-156">For example:</span></span>

```csharp
return ref DecimalArray[0];
```

<span data-ttu-id="dc0ea-157">Чтобы вызывающий объект имел возможность изменять состояние объекта, возвращаемое ссылочное значение должно храниться в переменной, которая явно определена как [ссылочная локальная переменная](#ref-locals).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-157">In order for the caller to modify the object's state, the reference return value must be stored to a variable that is explicitly defined as a [ref local](#ref-locals).</span></span>

<span data-ttu-id="dc0ea-158">Ниже приведен более полный пример возвращаемого значения ref, в котором показаны сигнатура метода и тело метода.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-158">Here is a more complete ref return example, showing both the method signature and method body.</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="dc0ea-159">Вызываемый метод может также объявить возвращаемое значение `ref readonly`, чтобы возвращать значения по ссылке, и запретить вызывающему коду изменять возвращенное значение.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-159">The called method may also declare the return value as `ref readonly` to return the value by reference, and enforce that the calling code cannot modify the returned value.</span></span> <span data-ttu-id="dc0ea-160">Вызывающий метод может обойтись без копирования возвращаемого значения, сохраняя его в локальной переменной [ref readonly](#ref-readonly-locals).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-160">The calling method can avoid copying the returned valued by storing the value in a local [ref readonly](#ref-readonly-locals) variable.</span></span>

<span data-ttu-id="dc0ea-161">Пример см. в разделе [Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных](#a-ref-returns-and-ref-locals-example).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-161">For an example, see [A ref returns and ref locals example](#a-ref-returns-and-ref-locals-example).</span></span>

## <a name="ref-locals"></a><span data-ttu-id="dc0ea-162">Ссылочные локальные переменные</span><span class="sxs-lookup"><span data-stu-id="dc0ea-162">Ref locals</span></span>

<span data-ttu-id="dc0ea-163">Ссылочная локальная переменная задает ссылку на значения, возвращаемые с помощью `return ref`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-163">A ref local variable is used to refer to values returned using `return ref`.</span></span> <span data-ttu-id="dc0ea-164">Ссылочная локальная переменная не может инициализироваться как не ссылочное возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-164">A ref local variable cannot be initialized to a non-ref return value.</span></span> <span data-ttu-id="dc0ea-165">Другими словами, правая часть инициализации должна быть ссылкой.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-165">In other words, the right-hand side of the initialization must be a reference.</span></span> <span data-ttu-id="dc0ea-166">Любые изменения в значении ссылочной локальной переменной отражаются в состоянии объекта, метод которого возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-166">Any modifications to the value of the ref local are reflected in the state of the object whose method returned the value by reference.</span></span>

<span data-ttu-id="dc0ea-167">Ссылочная локальная переменная определяется с помощью ключевого слова `ref` перед объявлением переменной, а также непосредственно перед вызовом метода, который возвращает значение по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-167">You define a ref local by using the `ref` keyword before the variable declaration, as well as immediately before the call to the method that returns the value by reference.</span></span>

<span data-ttu-id="dc0ea-168">Например, следующая инструкция определяет значение ссылочной локальной переменной, которое возвращается методом `GetEstimatedValue`:</span><span class="sxs-lookup"><span data-stu-id="dc0ea-168">For example, the following statement defines a ref local value that is returned by a method named `GetEstimatedValue`:</span></span>

```csharp
ref decimal estValue = ref Building.GetEstimatedValue();
```

<span data-ttu-id="dc0ea-169">Вы можете таким же образом обратиться к значению по ссылке.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-169">You can access a value by reference in the same way.</span></span> <span data-ttu-id="dc0ea-170">В некоторых случаях обращение к значению по ссылке повышает производительность, поскольку позволяет избежать потенциально затратной операции копирования.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-170">In some cases, accessing a value by reference increases performance by avoiding a potentially expensive copy operation.</span></span> <span data-ttu-id="dc0ea-171">Например, в следующей инструкции показано, как можно определить локальное ссылочное значение, используемое для ссылки на значение.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-171">For example, the following statement shows how one can define a ref local value that is used to reference a value.</span></span>

```csharp
ref VeryLargeStruct reflocal = ref veryLargeStruct;
```

<span data-ttu-id="dc0ea-172">В обоих примерах ключевое слово `ref` необходимо использовать в обоих местах. В противном случае возникает ошибка компилятора CS8172, "Невозможно инициализировать значением переменную по ссылке".</span><span class="sxs-lookup"><span data-stu-id="dc0ea-172">In both examples the `ref` keyword must be used in both places, or the compiler generates error CS8172, "Cannot initialize a by-reference variable with a value."</span></span>

<span data-ttu-id="dc0ea-173">Начиная с версии C# 7.3, переменная итерации инструкции `foreach` может иметь вид локальной ссылочной переменной или локальной ссылочной переменной только для чтения.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-173">Beginning with C# 7.3, the iteration variable of the `foreach` statement can be ref local or ref readonly local variable.</span></span> <span data-ttu-id="dc0ea-174">Дополнительные сведения см. в статье, посвященной [инструкции foreach](foreach-in.md).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-174">For more information, see the [foreach statement](foreach-in.md) article.</span></span>

<span data-ttu-id="dc0ea-175">Также, начиная с версии C# 7.3, вы можете переназначать ссылочную локальную переменную или ссылочную локальную переменную только для чтения с помощью [ссылочного оператора присваивания](../operators/assignment-operator.md#ref-assignment-operator).</span><span class="sxs-lookup"><span data-stu-id="dc0ea-175">Also beginning with C# 7.3, you can reassign a ref local or ref readonly local variable with the [ref assignment operator](../operators/assignment-operator.md#ref-assignment-operator).</span></span>

## <a name="ref-readonly-locals"></a><span data-ttu-id="dc0ea-176">Ссылочные локальные переменные только для чтения</span><span class="sxs-lookup"><span data-stu-id="dc0ea-176">Ref readonly locals</span></span>

<span data-ttu-id="dc0ea-177">Ссылочная локальная переменная только для чтения (ref readonly) позволяет сохранить ссылку на значения, возвращаемые методом или свойством, которые имеют в сигнатуре модификатор `ref readonly` и используют `return ref`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-177">A ref readonly local is used to refer to values returned by the method or property that has `ref readonly` in its signature and uses `return ref`.</span></span> <span data-ttu-id="dc0ea-178">Переменная `ref readonly` сочетает свойства локальной переменной `ref` и переменной `readonly`. Она является псевдонимом для хранилища, которому она присвоена, и не может изменять свое значение.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-178">A `ref readonly` variable combines the properties of a `ref` local variable with a `readonly` variable: it is an alias to the storage it's assigned to, and it cannot be modified.</span></span>

## <a name="a-ref-returns-and-ref-locals-example"></a><span data-ttu-id="dc0ea-179">Пример использования возвращаемых ссылочных значений и ссылочных локальных переменных</span><span class="sxs-lookup"><span data-stu-id="dc0ea-179">A ref returns and ref locals example</span></span>

<span data-ttu-id="dc0ea-180">В следующем примере определяется класс `Book`, содержащий два поля <xref:System.String>: `Title` и `Author`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-180">The following example defines a `Book` class that has two <xref:System.String> fields, `Title` and `Author`.</span></span> <span data-ttu-id="dc0ea-181">Также определяется класс `BookCollection`, который включает частный массив объектов `Book`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-181">It also defines a `BookCollection` class that includes a private array of `Book` objects.</span></span> <span data-ttu-id="dc0ea-182">Отдельные объекты книг возвращаются по ссылке путем вызова метода `GetBookByTitle`.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-182">Individual book objects are returned by reference by calling its `GetBookByTitle` method.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#4)]

<span data-ttu-id="dc0ea-183">Если вызывающий объект сохраняет значение, возвращаемое методом `GetBookByTitle`, в качестве ссылочной локальной переменной, изменения, которые этот объект вносит в возвращаемое значение, отражаются в объекте `BookCollection`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="dc0ea-183">When the caller stores the value returned by the `GetBookByTitle` method as a ref local, changes that the caller makes to the return value are reflected in the `BookCollection` object, as the following example shows.</span></span>

[!code-csharp[csrefKeywordsMethodParams#6](~/samples/snippets/csharp/language-reference/keywords/in-ref-out-modifier/RefParameterModifier.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="dc0ea-184">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="dc0ea-184">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dc0ea-185">См. также</span><span class="sxs-lookup"><span data-stu-id="dc0ea-185">See also</span></span>

- [<span data-ttu-id="dc0ea-186">Написание безопасного и эффективного кода</span><span class="sxs-lookup"><span data-stu-id="dc0ea-186">Write safe efficient code</span></span>](../../write-safe-efficient-code.md)
- [<span data-ttu-id="dc0ea-187">Возвращаемые значения ref и локальные переменные ref</span><span class="sxs-lookup"><span data-stu-id="dc0ea-187">Ref returns and ref locals</span></span>](../../programming-guide/classes-and-structs/ref-returns.md)
- [<span data-ttu-id="dc0ea-188">Условное выражение REF</span><span class="sxs-lookup"><span data-stu-id="dc0ea-188">Conditional ref expression</span></span>](../operators/conditional-operator.md#conditional-ref-expression)
- [<span data-ttu-id="dc0ea-189">Передача параметров</span><span class="sxs-lookup"><span data-stu-id="dc0ea-189">Passing Parameters</span></span>](../../programming-guide/classes-and-structs/passing-parameters.md)
- [<span data-ttu-id="dc0ea-190">Параметры методов</span><span class="sxs-lookup"><span data-stu-id="dc0ea-190">Method Parameters</span></span>](method-parameters.md)
- [<span data-ttu-id="dc0ea-191">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="dc0ea-191">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dc0ea-192">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="dc0ea-192">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dc0ea-193">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="dc0ea-193">C# Keywords</span></span>](index.md)
