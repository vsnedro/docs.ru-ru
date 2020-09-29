---
description: Псевдоним extern. Справочник по C#
title: Псевдоним extern. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 5ecafa5a989bc183d7f52ac3d4b4d50a81b36014
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203349"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="a7a72-103">Псевдоним extern (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="a7a72-103">extern alias (C# Reference)</span></span>

<span data-ttu-id="a7a72-104">Иногда может потребоваться сослаться на две версии сборок, которые имеют одинаковые полные имена типов.</span><span class="sxs-lookup"><span data-stu-id="a7a72-104">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="a7a72-105">Например, если необходимо использовать две или более версии сборки в одном приложении.</span><span class="sxs-lookup"><span data-stu-id="a7a72-105">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="a7a72-106">Используя внешний псевдоним сборки, пространства имен для каждой сборки можно перенести внутрь пространств имен корневого уровня с именованием по псевдониму, что позволяет использовать их в одном файле.</span><span class="sxs-lookup"><span data-stu-id="a7a72-106">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7a72-107">Ключевое слово [extern](./extern.md) также используется в качестве модификатора метода, объявляющего метод, написанный в неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="a7a72-107">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="a7a72-108">Для ссылки на две сборки с одинаковыми полными именами типов псевдоним необходимо указать в командной строке следующим образом:</span><span class="sxs-lookup"><span data-stu-id="a7a72-108">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="a7a72-109">При этом создаются внешние псевдонимы `GridV1` и `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="a7a72-109">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="a7a72-110">Чтобы использовать эти псевдонимы в программе, сошлитесь на них с помощью ключевого слова `extern`.</span><span class="sxs-lookup"><span data-stu-id="a7a72-110">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="a7a72-111">Пример:</span><span class="sxs-lookup"><span data-stu-id="a7a72-111">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="a7a72-112">Каждое объявление псевдонима extern создает дополнительное пространство имен корневого уровня, которое является параллельным для глобального пространства имен (но не находится в его пределах).</span><span class="sxs-lookup"><span data-stu-id="a7a72-112">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="a7a72-113">Таким образом, на типы из каждой сборки можно ссылаться без неоднозначности, используя их полное имя, размещенное в соответствующем пространстве имен-псевдониме.</span><span class="sxs-lookup"><span data-stu-id="a7a72-113">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="a7a72-114">В предыдущем примере `GridV1::Grid` является элементом управления сетки из `grid.dll`, а `GridV2::Grid` — элементом управления сетки из `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="a7a72-114">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="a7a72-115">Использование Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7a72-115">Using Visual Studio</span></span>

<span data-ttu-id="a7a72-116">Если вы используете Visual Studio, псевдонимы можно указать аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="a7a72-116">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="a7a72-117">Добавьте ссылку на *grid.dll* и *grid20.dll* в проект в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a7a72-117">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="a7a72-118">Откройте вкладку свойств и измените псевдонимы с глобальных на GridV1 и GridV2 соответственно.</span><span class="sxs-lookup"><span data-stu-id="a7a72-118">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="a7a72-119">Используйте эти псевдонимы так же, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="a7a72-119">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="a7a72-120">Теперь можно создать псевдоним для пространства имен или типа, *используя директиву псевдонимов using*.</span><span class="sxs-lookup"><span data-stu-id="a7a72-120">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="a7a72-121">Дополнительные сведения см. в разделе [Директива using](using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="a7a72-121">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="a7a72-122">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="a7a72-122">C# Language Specification</span></span>  

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7a72-123">См. также</span><span class="sxs-lookup"><span data-stu-id="a7a72-123">See also</span></span>

- [<span data-ttu-id="a7a72-124">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="a7a72-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a7a72-125">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a7a72-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a7a72-126">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="a7a72-126">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="a7a72-127">:: Оператор</span><span class="sxs-lookup"><span data-stu-id="a7a72-127">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="a7a72-128">-reference (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="a7a72-128">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
