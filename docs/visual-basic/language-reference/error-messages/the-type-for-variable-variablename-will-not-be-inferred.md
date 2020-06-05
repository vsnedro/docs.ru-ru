---
title: Тип для переменной <variablename> не будет определен, так как она привязана к полю во включающей области
ms.date: 07/20/2015
f1_keywords:
- vbc42110
- bc42110
helpviewer_keywords:
- BC42110
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
ms.openlocfilehash: 98aeb5699fdd5e5e538a205acd37436019c3fc03
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84363050"
---
# <a name="the-type-for-variable-variablename-will-not-be-inferred-because-it-is-bound-to-a-field-in-an-enclosing-scope"></a><span data-ttu-id="dfb1f-102">Тип для переменной \<variablename> не будет определен, так как она привязана к полю во включающей области</span><span class="sxs-lookup"><span data-stu-id="dfb1f-102">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope</span></span>

<span data-ttu-id="dfb1f-103">Тип для переменной " \<variablename> " не будет определен, так как он привязан к полю во внешней области видимости.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-103">The type for variable '\<variablename>' will not be inferred because it is bound to a field in an enclosing scope.</span></span> <span data-ttu-id="dfb1f-104">Либо измените имя " \<variablename> ", либо используйте полное имя (например, "Me. variablename" или "MyBase. variablename").</span><span class="sxs-lookup"><span data-stu-id="dfb1f-104">Either change the name of '\<variablename>', or use the fully qualified name (for example, 'Me.variablename' or 'MyBase.variablename').</span></span>

<span data-ttu-id="dfb1f-105">Переменная цикла в коде имеет то же имя, что и поле класса или другой включающей области.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-105">A loop control variable in your code has the same name as a field of the class or other enclosing scope.</span></span> <span data-ttu-id="dfb1f-106">Так как переменная управления используется без `As` предложения, она привязывается к полю во включающей области, и компилятор не создает для него новую переменную или не выводит ее тип.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-106">Because the control variable is used without an `As` clause, it is bound to the field in the enclosing scope, and the compiler does not create a new variable for it or infer its type.</span></span>

<span data-ttu-id="dfb1f-107">В следующем примере `Index` Переменная элемента управления в `For` операторе привязана к `Index` полю в `Customer` классе.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-107">In the following example, `Index`, the control variable in the `For` statement, is bound to the `Index` field in the `Customer` class.</span></span> <span data-ttu-id="dfb1f-108">Компилятор не создает новую переменную для управляющей переменной `Index` или выводит ее тип.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-108">The compiler does not create a new variable for the control variable `Index` or infer its type.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

    ' The following line will raise this warning.
        For Index = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

<span data-ttu-id="dfb1f-109">По умолчанию данное сообщение является предупреждением.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-109">By default, this message is a warning.</span></span> <span data-ttu-id="dfb1f-110">Дополнительные сведения о том, как скрыть предупреждения или как рассматривать предупреждения как ошибки, см. в разделе [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="dfb1f-110">For information about how to hide warnings or how to treat warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

<span data-ttu-id="dfb1f-111">**Идентификатор ошибки:** BC42110</span><span class="sxs-lookup"><span data-stu-id="dfb1f-111">**Error ID:** BC42110</span></span>

### <a name="to-address-this-warning"></a><span data-ttu-id="dfb1f-112">Устранение предупреждения</span><span class="sxs-lookup"><span data-stu-id="dfb1f-112">To address this warning</span></span>

- <span data-ttu-id="dfb1f-113">Сделайте переменную управления циклом локальной, изменив ее имя на идентификатор, который не является именем поля класса.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-113">Make the loop control variable local by changing its name to an identifier that is not also the name of a field of the class.</span></span>

  ```vb
  For I = 1 To 10
  ```

- <span data-ttu-id="dfb1f-114">Уточните, что управляющая переменная цикла привязывается к полю класса путем добавления префикса `Me.` к имени переменной.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-114">Clarify that the loop control variable binds to the class field by prefixing `Me.` to the variable name.</span></span>

  ```vb
  For Me.Index = 1 To 10
  ```

- <span data-ttu-id="dfb1f-115">Вместо того чтобы полагаться на вывод локального типа, используйте `As` предложение, чтобы указать тип для управляющей переменной цикла.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-115">Instead of relying on local type inference, use an `As` clause to specify a type for the loop control variable.</span></span>

  ```vb
  For Index As Integer = 1 To 10
  ```

## <a name="example"></a><span data-ttu-id="dfb1f-116">Пример</span><span class="sxs-lookup"><span data-stu-id="dfb1f-116">Example</span></span>
 <span data-ttu-id="dfb1f-117">В следующем коде показан предыдущий пример с первым исправлением.</span><span class="sxs-lookup"><span data-stu-id="dfb1f-117">The following code shows the earlier example with the first correction in place.</span></span>

```vb
Class Customer

    ' The class has a field named Index.
    Private Index As Integer

    Sub Main()

        For I = 1 To 10
            ' ...
        Next

    End Sub
End Class
```

## <a name="see-also"></a><span data-ttu-id="dfb1f-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="dfb1f-118">See also</span></span>

- [<span data-ttu-id="dfb1f-119">Оператор Option Infer</span><span class="sxs-lookup"><span data-stu-id="dfb1f-119">Option Infer Statement</span></span>](../statements/option-infer-statement.md)
- [<span data-ttu-id="dfb1f-120">Оператор For Each…Next</span><span class="sxs-lookup"><span data-stu-id="dfb1f-120">For Each...Next Statement</span></span>](../statements/for-each-next-statement.md)
- [<span data-ttu-id="dfb1f-121">Оператор For…Next</span><span class="sxs-lookup"><span data-stu-id="dfb1f-121">For...Next Statement</span></span>](../statements/for-next-statement.md)
- [<span data-ttu-id="dfb1f-122">Практическое руководство. Ссылка на текущий экземпляр объекта</span><span class="sxs-lookup"><span data-stu-id="dfb1f-122">How to: Refer to the Current Instance of an Object</span></span>](../../programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)
- [<span data-ttu-id="dfb1f-123">Вывод локального типа</span><span class="sxs-lookup"><span data-stu-id="dfb1f-123">Local Type Inference</span></span>](../../programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="dfb1f-124">Me, My, MyBase и MyClass</span><span class="sxs-lookup"><span data-stu-id="dfb1f-124">Me, My, MyBase, and MyClass</span></span>](../../programming-guide/program-structure/me-my-mybase-and-myclass.md)
