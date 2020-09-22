---
description: protected internal. Справочник по C#
title: protected internal. Справочник по C#
ms.date: 11/15/2017
f1_keywords:
- protectedinternal_CSharpKeyword
author: sputier
ms.openlocfilehash: f22de104154df74f02c048b1209eeac754a03e64
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90536810"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="980bd-103">protected internal (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="980bd-103">protected internal (C# Reference)</span></span>

<span data-ttu-id="980bd-104">Комбинация ключевых слов `protected internal` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="980bd-104">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="980bd-105">Доступ к членам с модификатором доступа protected internal может осуществляться из текущей сборки или типов, которые являются производными от содержащего класса.</span><span class="sxs-lookup"><span data-stu-id="980bd-105">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="980bd-106">Сравнение модификатора `protected internal` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="980bd-106">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

## <a name="example"></a><span data-ttu-id="980bd-107">Пример</span><span class="sxs-lookup"><span data-stu-id="980bd-107">Example</span></span>

<span data-ttu-id="980bd-108">Член базового класса с модификатором доступа protected internal доступен из любого типа в пределах содержащей сборки.</span><span class="sxs-lookup"><span data-stu-id="980bd-108">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="980bd-109">Он также доступен в производном классе, расположенном в другой сборке, только в том случае, если доступ осуществляется через переменную типа производного класса.</span><span class="sxs-lookup"><span data-stu-id="980bd-109">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="980bd-110">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="980bd-110">For example, consider the following code segment:</span></span>

```csharp
// Assembly1.cs
// Compile with: /target:library
public class BaseClass
{
   protected internal int myValue = 0;
}

class TestAccess
{
    void Access()
    {
        var baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass : BaseClass
{
    static void Main()
    {
        var baseObject = new BaseClass();
        var derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10;

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
}
```

<span data-ttu-id="980bd-111">Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="980bd-111">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="980bd-112">Первый файл содержит открытый базовый класс, `BaseClass`, и еще один класс, `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="980bd-112">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="980bd-113">`BaseClass` владеет членом protected internal, `myValue`, доступ к которому осуществляется типом `TestAccess`.</span><span class="sxs-lookup"><span data-stu-id="980bd-113">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span>
<span data-ttu-id="980bd-114">Во втором файле попытка получить доступ к `myValue` через экземпляр `BaseClass` приведет к ошибке во время доступа к этому члену через экземпляр производного класса. `DerivedClass` гарантирует успешное выполнение.</span><span class="sxs-lookup"><span data-stu-id="980bd-114">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span>

<span data-ttu-id="980bd-115">Элементы структуры не могут иметь модификатор `protected internal`, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="980bd-115">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="980bd-116">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="980bd-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="980bd-117">См. также</span><span class="sxs-lookup"><span data-stu-id="980bd-117">See also</span></span>

- [<span data-ttu-id="980bd-118">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="980bd-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="980bd-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="980bd-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="980bd-120">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="980bd-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="980bd-121">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="980bd-121">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="980bd-122">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="980bd-122">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="980bd-123">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="980bd-123">Modifiers</span></span>](index.md)
- [<span data-ttu-id="980bd-124">public</span><span class="sxs-lookup"><span data-stu-id="980bd-124">public</span></span>](public.md)
- [<span data-ttu-id="980bd-125">private</span><span class="sxs-lookup"><span data-stu-id="980bd-125">private</span></span>](private.md)
- [<span data-ttu-id="980bd-126">internal</span><span class="sxs-lookup"><span data-stu-id="980bd-126">internal</span></span>](internal.md)
- <span data-ttu-id="980bd-127">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="980bd-127">[Security concerns for internal virtual keywords](/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
