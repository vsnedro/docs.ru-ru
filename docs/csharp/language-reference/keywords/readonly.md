---
description: Справочник по C#. Ключевое слово readonly
title: Справочник по C#. Ключевое слово readonly
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: b1bab5af18216fcef2162179493dbbb59e3470cf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137179"
---
# <a name="readonly-c-reference"></a><span data-ttu-id="1d0ce-103">readonly (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="1d0ce-103">readonly (C# Reference)</span></span>

<span data-ttu-id="1d0ce-104">Ключевое слово `readonly` — это модификатор, который может использоваться в четырех контекстах:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-104">The `readonly` keyword is a modifier that can be used in four contexts:</span></span>

- <span data-ttu-id="1d0ce-105">В [объявлении поля](#readonly-field-example)`readonly` указывает на то, что присвоение значения полю может происходить только при объявлении или в конструкторе этого класса.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-105">In a [field declaration](#readonly-field-example), `readonly` indicates that assignment to the field can only occur as part of the declaration or in a constructor in the same class.</span></span> <span data-ttu-id="1d0ce-106">Полю только для чтения можно несколько раз назначить значения в объявлении поля и в конструкторе.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-106">A readonly field can be assigned and reassigned multiple times within the field declaration and constructor.</span></span>
  
  <span data-ttu-id="1d0ce-107">Поле `readonly` нельзя изменять после выхода из конструктора.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-107">A `readonly` field can't be assigned after the constructor exits.</span></span> <span data-ttu-id="1d0ce-108">Это правило влечет за собой разные последствия для типов значений и ссылочных типов:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-108">This rule has different implications for value types and reference types:</span></span>
  
  - <span data-ttu-id="1d0ce-109">Поскольку типы значений содержат данные, поле `readonly` с типом значения является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-109">Because value types directly contain their data, a field that is a  `readonly` value type is immutable.</span></span>
  - <span data-ttu-id="1d0ce-110">Ссылочные типы содержат только ссылку на соответствующие данные, а значит поле `readonly` ссылочного типа будет всегда ссылаться на один объект.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-110">Because reference types contain a reference to their data, a field that is a `readonly` reference type must always refer to the same object.</span></span> <span data-ttu-id="1d0ce-111">Но сам этот объект не является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-111">That object isn't immutable.</span></span> <span data-ttu-id="1d0ce-112">Модификатор `readonly` запрещает замену поля другим экземпляром ссылочного типа.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-112">The `readonly` modifier prevents the field from being replaced by a different instance of the reference type.</span></span> <span data-ttu-id="1d0ce-113">Но этот модификатор не препятствует изменению данных экземпляра, на которое ссылается поле только для чтения, в том числе через это поле.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-113">However, the modifier doesn't prevent the instance data of the field from being modified through the read-only field.</span></span>

  > [!WARNING]
  > <span data-ttu-id="1d0ce-114">Видимый извне тип, который содержит видимое извне и доступное только для чтения поле с изменяемым ссылочным типом, может представлять уязвимость и приводить к предупреждению [CA2104](/visualstudio/code-quality/ca2104): Не объявляйте изменяющиеся ссылочные типы только для чтения.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-114">An externally visible type that contains an externally visible read-only field that is a mutable reference type may be a security vulnerability and may trigger warning [CA2104](/visualstudio/code-quality/ca2104) : "Do not declare read only mutable reference types."</span></span>

- <span data-ttu-id="1d0ce-115">В определении типа `readonly struct` объект `readonly` указывает на то, что тип структуры является неизменяемым.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-115">In a `readonly struct` type definition, `readonly` indicates that the structure type is immutable.</span></span> <span data-ttu-id="1d0ce-116">Дополнительные сведения см. в описании [структуры `readonly`](../builtin-types/struct.md#readonly-struct) в статье [Типы структур](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="1d0ce-116">For more information, see the [`readonly` struct](../builtin-types/struct.md#readonly-struct) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="1d0ce-117">В объявлении члена экземпляра в типе структуры `readonly` указывает на то, что член экземпляра не изменяет состояние структуры.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-117">In an instance member declaration within a structure type, `readonly` indicates that an instance member doesn't modify the state of the structure.</span></span> <span data-ttu-id="1d0ce-118">Дополнительные сведения см. в разделе о [членах экземпляров `readonly`](../builtin-types/struct.md#readonly-instance-members) в статье [Типы структур](../builtin-types/struct.md).</span><span class="sxs-lookup"><span data-stu-id="1d0ce-118">For more information, see the [`readonly` instance members](../builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../builtin-types/struct.md) article.</span></span>
- <span data-ttu-id="1d0ce-119">В [возврате метода `ref readonly`](#ref-readonly-return-example) модификатор `readonly` указывает, что метод возвращает ссылку, и записи для этой ссылки не допускаются.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-119">In a [`ref readonly` method return](#ref-readonly-return-example), the `readonly` modifier indicates that method returns a reference and writes aren't allowed to that reference.</span></span>

<span data-ttu-id="1d0ce-120">Контексты `readonly struct` и `ref readonly` были добавлены в C# 7.2.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-120">The `readonly struct` and `ref readonly` contexts were added in C# 7.2.</span></span> <span data-ttu-id="1d0ce-121">Члены структуры `readonly` добавлены в C# 8.0</span><span class="sxs-lookup"><span data-stu-id="1d0ce-121">`readonly` struct members were added in C# 8.0</span></span>

## <a name="readonly-field-example"></a><span data-ttu-id="1d0ce-122">Пример поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="1d0ce-122">Readonly field example</span></span>

<span data-ttu-id="1d0ce-123">В этом примере значение поля `year` нельзя изменить в методе `ChangeYear`, несмотря на то, что в конструкторе класса ему присваивается значение:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-123">In this example, the value of the field `year` can't be changed in the method `ChangeYear`, even though it's assigned a value in the class constructor:</span></span>

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

<span data-ttu-id="1d0ce-124">Можно присвоить значение полю `readonly` только в следующих контекстах:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-124">You can assign a value to a `readonly` field only in the following contexts:</span></span>

- <span data-ttu-id="1d0ce-125">Когда переменная инициализируется в объявлении, например:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-125">When the variable is initialized in the declaration, for example:</span></span>

  ```csharp
  public readonly int y = 5;
  ```

- <span data-ttu-id="1d0ce-126">В конструкторе экземпляра класса, содержащего объявление поля экземпляра.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-126">In an instance constructor of the class that contains the instance field declaration.</span></span>
- <span data-ttu-id="1d0ce-127">В статическом конструкторе класса, содержащего объявление статического поля.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-127">In the static constructor of the class that contains the static field declaration.</span></span>

<span data-ttu-id="1d0ce-128">Эти контексты конструктора являются единственными, в которых можно передавать поле `readonly` в качестве параметра [out](out-parameter-modifier.md) или [ref](ref.md).</span><span class="sxs-lookup"><span data-stu-id="1d0ce-128">These constructor contexts are also the only contexts in which it's valid to pass a `readonly` field as an [out](out-parameter-modifier.md) or [ref](ref.md) parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="1d0ce-129">Ключевое слово `readonly` отличается от ключевого слова [const](const.md).</span><span class="sxs-lookup"><span data-stu-id="1d0ce-129">The `readonly` keyword is different from the [const](const.md) keyword.</span></span> <span data-ttu-id="1d0ce-130">Поле `const` может быть инициализировано только при объявлении поля.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-130">A `const` field can only be initialized at the declaration of the field.</span></span> <span data-ttu-id="1d0ce-131">Поле `readonly` может быть назначено несколько раз в объявлении поля и в любом конструкторе.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-131">A `readonly` field can be assigned multiple times in the field declaration and in any constructor.</span></span> <span data-ttu-id="1d0ce-132">Таким образом, поля `readonly` могут иметь разные значения в зависимости от использованного конструктора.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-132">Therefore, `readonly` fields can have different values depending on the constructor used.</span></span> <span data-ttu-id="1d0ce-133">К тому же, поскольку поле `const` является константой времени компиляции, поле `readonly` можно использовать для констант времени выполнения, как в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-133">Also, while a `const` field is a compile-time constant, the `readonly` field can be used for run-time constants as in the following example:</span></span>
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

<span data-ttu-id="1d0ce-134">В предыдущем примере при использовании такого оператора:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-134">In the preceding example, if you use a statement like the following example:</span></span>

```csharp
p2.y = 66;        // Error
```

<span data-ttu-id="1d0ce-135">будет отображено сообщение об ошибке компилятора:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-135">you'll get the compiler error message:</span></span>

<span data-ttu-id="1d0ce-136">**Присваивание значений доступному только для чтения полю допускается только в конструкторе и в инициализаторе переменных.**</span><span class="sxs-lookup"><span data-stu-id="1d0ce-136">**A readonly field cannot be assigned to (except in a constructor or a variable initializer)**</span></span>

## <a name="ref-readonly-return-example"></a><span data-ttu-id="1d0ce-137">Пример возвращаемой ссылки только для чтения</span><span class="sxs-lookup"><span data-stu-id="1d0ce-137">Ref readonly return example</span></span>

<span data-ttu-id="1d0ce-138">Модификатор `readonly` в `ref return` указывает, что возвращаемую ссылку нельзя изменить.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-138">The `readonly` modifier on a `ref return` indicates that the returned reference can't be modified.</span></span> <span data-ttu-id="1d0ce-139">Следующий пример возвращает ссылку на источник.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-139">The following example returns a reference to the origin.</span></span> <span data-ttu-id="1d0ce-140">Он использует модификатор `readonly`, чтобы указать, что вызывающие объекты не могут изменять источник:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-140">It uses the `readonly` modifier to indicate that callers can't modify the origin:</span></span>

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

<span data-ttu-id="1d0ce-141">Необязательно должен возвращаться тип `readonly struct`.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-141">The type returned doesn't need to be a `readonly struct`.</span></span> <span data-ttu-id="1d0ce-142">Любой тип, возвращаемый из `ref`, может возвращаться из `ref readonly`.</span><span class="sxs-lookup"><span data-stu-id="1d0ce-142">Any type that can be returned by `ref` can be returned by `ref readonly`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1d0ce-143">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="1d0ce-143">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

<span data-ttu-id="1d0ce-144">Вы также можете ознакомиться с предложениями языковых спецификаций:</span><span class="sxs-lookup"><span data-stu-id="1d0ce-144">You can also see the language specification proposals:</span></span>

- [<span data-ttu-id="1d0ce-145">Ссылка и структура readonly</span><span class="sxs-lookup"><span data-stu-id="1d0ce-145">readonly ref and readonly struct</span></span>](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [<span data-ttu-id="1d0ce-146">Члены структуры readonly</span><span class="sxs-lookup"><span data-stu-id="1d0ce-146">readonly struct members</span></span>](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a><span data-ttu-id="1d0ce-147">См. также</span><span class="sxs-lookup"><span data-stu-id="1d0ce-147">See also</span></span>

- [<span data-ttu-id="1d0ce-148">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="1d0ce-148">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1d0ce-149">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1d0ce-149">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1d0ce-150">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="1d0ce-150">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1d0ce-151">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="1d0ce-151">Modifiers</span></span>](index.md)
- [<span data-ttu-id="1d0ce-152">const</span><span class="sxs-lookup"><span data-stu-id="1d0ce-152">const</span></span>](const.md)
- [<span data-ttu-id="1d0ce-153">Поля</span><span class="sxs-lookup"><span data-stu-id="1d0ce-153">Fields</span></span>](../../programming-guide/classes-and-structs/fields.md)
