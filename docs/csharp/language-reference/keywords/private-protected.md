---
title: Справочник по C#. Комбинация ключевых слов private protected
ms.date: 11/15/2017
f1_keywords:
- privateprotected_CSharpKeyword
author: sputier
ms.openlocfilehash: 94ef55d7e13841f81b036f52659b215e22a3a0d7
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301805"
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="8ffb3-102">private protected (справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="8ffb3-102">private protected (C# Reference)</span></span>

<span data-ttu-id="8ffb3-103">Комбинация ключевых слов `private protected` является модификатором доступа к члену.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="8ffb3-104">К члену private protected имеют доступ типы, производные от содержащего класса, но только в пределах содержащей сборки.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="8ffb3-105">Сравнение модификатора `private protected` с другими модификаторами доступа см. в разделе [Уровни доступности](accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="8ffb3-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](accessibility-levels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8ffb3-106">Модификатор доступа `private protected` допустим в C# 7.2 и более поздних версий.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-106">The `private protected` access modifier is valid in C# version 7.2 and later.</span></span>

## <a name="example"></a><span data-ttu-id="8ffb3-107">Пример</span><span class="sxs-lookup"><span data-stu-id="8ffb3-107">Example</span></span>

<span data-ttu-id="8ffb3-108">Член базового класса private protected доступен из производных типов в содержащей сборке только в том случае, если статический тип переменной является типом производного класса.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-108">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="8ffb3-109">Для примера рассмотрим следующий сегмент кода:</span><span class="sxs-lookup"><span data-stu-id="8ffb3-109">For example, consider the following code segment:</span></span>

```csharp
public class BaseClass
{
    private protected int myValue = 0;
}

public class DerivedClass1 : BaseClass
{
    void Access()
    {
        var baseObject = new BaseClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 5;

        // OK, accessed through the current derived class instance
        myValue = 5;
    }
}
```

```csharp
// Assembly2.cs
// Compile with: /reference:Assembly1.dll
class DerivedClass2 : BaseClass
{
    void Access()
    {
        // Error CS0122, because myValue can only be
        // accessed by types in Assembly1
        // myValue = 10;
    }
}
```

<span data-ttu-id="8ffb3-110">Этот пример содержит два файла, `Assembly1.cs` и `Assembly2.cs`.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span>
<span data-ttu-id="8ffb3-111">Первый файл содержит открытый базовый класс, `BaseClass`, и производный от него тип, `DerivedClass1`.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-111">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="8ffb3-112">`BaseClass` владеет членом private protected, `myValue`, к которому `DerivedClass1` пытается получить доступ двумя способами.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-112">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="8ffb3-113">Первая попытка доступа к `myValue` через экземпляр `BaseClass` приведет к ошибке.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-113">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="8ffb3-114">Однако попытка использовать его в качестве наследуемого члена в `DerivedClass1` завершится успешно.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-114">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>

<span data-ttu-id="8ffb3-115">Во втором файле попытка получить доступ к `myValue` в качестве наследуемого члена `DerivedClass2` приведет к ошибке, поскольку он доступен только для производных типов в Assembly1.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-115">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span>

<span data-ttu-id="8ffb3-116">Если `Assembly1.cs` содержит <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> с именем `Assembly2`, производный класс `DerivedClass1` будет иметь доступ к членам `private protected`, объявленным в `BaseClass`.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-116">If `Assembly1.cs` contains an <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> that names `Assembly2`, the derived class `DerivedClass1` will have access to `private protected` members declared in `BaseClass`.</span></span> <span data-ttu-id="8ffb3-117">`InternalsVisibleTo` делает члены `private protected` видимыми для производных классов в других сборках.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-117">`InternalsVisibleTo` makes `private protected` members visible to derived classes in other assemblies.</span></span>

<span data-ttu-id="8ffb3-118">Элементы структуры не могут иметь модификатор `private protected`, поскольку структура не может наследоваться.</span><span class="sxs-lookup"><span data-stu-id="8ffb3-118">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8ffb3-119">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="8ffb3-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8ffb3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="8ffb3-120">See also</span></span>

- [<span data-ttu-id="8ffb3-121">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="8ffb3-121">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8ffb3-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="8ffb3-122">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8ffb3-123">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="8ffb3-123">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="8ffb3-124">Модификаторы доступа</span><span class="sxs-lookup"><span data-stu-id="8ffb3-124">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="8ffb3-125">Уровни доступности</span><span class="sxs-lookup"><span data-stu-id="8ffb3-125">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="8ffb3-126">Модификаторы</span><span class="sxs-lookup"><span data-stu-id="8ffb3-126">Modifiers</span></span>](index.md)
- [<span data-ttu-id="8ffb3-127">public</span><span class="sxs-lookup"><span data-stu-id="8ffb3-127">public</span></span>](public.md)
- [<span data-ttu-id="8ffb3-128">private</span><span class="sxs-lookup"><span data-stu-id="8ffb3-128">private</span></span>](private.md)
- [<span data-ttu-id="8ffb3-129">internal</span><span class="sxs-lookup"><span data-stu-id="8ffb3-129">internal</span></span>](internal.md)
- <span data-ttu-id="8ffb3-130">[Вопросы безопасности, связанные с использованием ключевых слов internal virtual](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="8ffb3-130">[Security concerns for internal virtual keywords](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/heyd8kky(v=vs.100))</span></span>
