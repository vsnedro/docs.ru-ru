---
title: Первый операнд в двоичном выражении If должен поддерживать значение NULL или быть ссылочного типа
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: bca9b74a68815b4e5a3bb2dc114b9031cdf24099
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162743"
---
# <a name="bc33107-first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a><span data-ttu-id="180cd-102">BC33107: первый операнд в двоичном выражении if должен допускать значение null или ссылочный тип</span><span class="sxs-lookup"><span data-stu-id="180cd-102">BC33107: First operand in a binary 'If' expression must be nullable or a reference type</span></span>

<span data-ttu-id="180cd-103">`If`Выражение может принимать либо два, либо три аргумента.</span><span class="sxs-lookup"><span data-stu-id="180cd-103">An `If` expression can take either two or three arguments.</span></span> <span data-ttu-id="180cd-104">При отправке только двух аргументов первый аргумент должен быть ссылочным типом или типом значения, допускающим значение null.</span><span class="sxs-lookup"><span data-stu-id="180cd-104">When you send only two arguments, the first argument must be a reference type or a nullable value type.</span></span> <span data-ttu-id="180cd-105">Если первый аргумент принимает значение, отличное от, то `Nothing` возвращается.</span><span class="sxs-lookup"><span data-stu-id="180cd-105">If the first argument evaluates to anything other than `Nothing`, its value is returned.</span></span> <span data-ttu-id="180cd-106">Если первый аргумент имеет значение `Nothing` , то вычисляется и возвращается второй аргумент.</span><span class="sxs-lookup"><span data-stu-id="180cd-106">If the first argument evaluates to `Nothing`, the second argument is evaluated and returned.</span></span>

 <span data-ttu-id="180cd-107">Например, следующий код содержит два `If` выражения: один с тремя аргументами и один с двумя аргументами.</span><span class="sxs-lookup"><span data-stu-id="180cd-107">For example, the following code contains two `If` expressions, one with three arguments and one with two arguments.</span></span> <span data-ttu-id="180cd-108">Выражения вычисляют и возвращают одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="180cd-108">The expressions calculate and return the same value.</span></span>

```vb
' firstChoice is a nullable value type.
Dim firstChoice? As Integer = Nothing
Dim secondChoice As Integer = 1128
' If expression with three arguments.
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))
' If expression with two arguments.
Console.WriteLine(If(firstChoice, secondChoice))
```

 <span data-ttu-id="180cd-109">Эта ошибка возникает в следующих выражениях:</span><span class="sxs-lookup"><span data-stu-id="180cd-109">The following expressions cause this error:</span></span>

```vb
Dim choice1 = 4
Dim choice2 = 5
Dim booleanVar = True

' Not valid.
'Console.WriteLine(If(choice1 < choice2, 1))
' Not valid.
'Console.WriteLine(If(booleanVar, "Test returns True."))
```

 <span data-ttu-id="180cd-110">**Идентификатор ошибки:** BC33107</span><span class="sxs-lookup"><span data-stu-id="180cd-110">**Error ID:** BC33107</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="180cd-111">Исправление ошибки</span><span class="sxs-lookup"><span data-stu-id="180cd-111">To correct this error</span></span>

- <span data-ttu-id="180cd-112">Если не удается изменить код, чтобы первый аргумент являлся типом значения, допускающим значение null, или ссылочным типом, попробуйте преобразовать в выражение с тремя аргументами `If` или в `If...Then...Else` оператор.</span><span class="sxs-lookup"><span data-stu-id="180cd-112">If you cannot change the code so that the first argument is a nullable value type or reference type, consider converting to a three-argument `If` expression, or to an `If...Then...Else` statement.</span></span>

```vb
Console.WriteLine(If(choice1 < choice2, 1, 2))
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))
```

## <a name="see-also"></a><span data-ttu-id="180cd-113">См. также</span><span class="sxs-lookup"><span data-stu-id="180cd-113">See also</span></span>

- [<span data-ttu-id="180cd-114">Оператор If</span><span class="sxs-lookup"><span data-stu-id="180cd-114">If Operator</span></span>](../operators/if-operator.md)
- [<span data-ttu-id="180cd-115">Оператор If…Then…Else</span><span class="sxs-lookup"><span data-stu-id="180cd-115">If...Then...Else Statement</span></span>](../statements/if-then-else-statement.md)
- [<span data-ttu-id="180cd-116">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="180cd-116">Nullable Value Types</span></span>](../../programming-guide/language-features/data-types/nullable-value-types.md)
