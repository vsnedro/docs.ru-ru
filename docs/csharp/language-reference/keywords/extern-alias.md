---
title: Псевдоним extern. Справочник по C#
ms.date: 07/20/2015
f1_keywords:
- alias_CSharpKeyword
helpviewer_keywords:
- extern alias keyword [C#]
- aliases [C#], extern keyword
- aliases, extern keyword
ms.assetid: f487bf4f-c943-4fca-851b-e540c83d9027
ms.openlocfilehash: 891e56b064f8a327abe28293223a85b9d95e8fd3
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301818"
---
# <a name="extern-alias-c-reference"></a><span data-ttu-id="6e497-102">Псевдоним extern (Справочник по C#)</span><span class="sxs-lookup"><span data-stu-id="6e497-102">extern alias (C# Reference)</span></span>
<span data-ttu-id="6e497-103">Иногда может потребоваться сослаться на две версии сборок, которые имеют одинаковые полные имена типов.</span><span class="sxs-lookup"><span data-stu-id="6e497-103">You might have to reference two versions of assemblies that have the same fully-qualified type names.</span></span> <span data-ttu-id="6e497-104">Например, если необходимо использовать две или более версии сборки в одном приложении.</span><span class="sxs-lookup"><span data-stu-id="6e497-104">For example, you might have to use two or more versions of an assembly in the same application.</span></span> <span data-ttu-id="6e497-105">Используя внешний псевдоним сборки, пространства имен для каждой сборки можно перенести внутрь пространств имен корневого уровня с именованием по псевдониму, что позволяет использовать их в одном файле.</span><span class="sxs-lookup"><span data-stu-id="6e497-105">By using an external assembly alias, the namespaces from each assembly can be wrapped inside root-level namespaces named by the alias, which enables them to be used in the same file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e497-106">Ключевое слово [extern](./extern.md) также используется в качестве модификатора метода, объявляющего метод, написанный в неуправляемом коде.</span><span class="sxs-lookup"><span data-stu-id="6e497-106">The [extern](./extern.md) keyword is also used as a method modifier, declaring a method written in unmanaged code.</span></span>  
  
 <span data-ttu-id="6e497-107">Для ссылки на две сборки с одинаковыми полными именами типов псевдоним необходимо указать в командной строке следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6e497-107">To reference two assemblies with the same fully-qualified type names, an alias must be specified at a command prompt, as follows:</span></span>  
  
 `/r:GridV1=grid.dll`  
  
 `/r:GridV2=grid20.dll`  
  
 <span data-ttu-id="6e497-108">При этом создаются внешние псевдонимы `GridV1` и `GridV2`.</span><span class="sxs-lookup"><span data-stu-id="6e497-108">This creates the external aliases `GridV1` and `GridV2`.</span></span> <span data-ttu-id="6e497-109">Чтобы использовать эти псевдонимы в программе, сошлитесь на них с помощью ключевого слова `extern`.</span><span class="sxs-lookup"><span data-stu-id="6e497-109">To use these aliases from within a program, reference them by using the `extern` keyword.</span></span> <span data-ttu-id="6e497-110">Пример:</span><span class="sxs-lookup"><span data-stu-id="6e497-110">For example:</span></span>  
  
 `extern alias GridV1;`  
  
 `extern alias GridV2;`  
  
 <span data-ttu-id="6e497-111">Каждое объявление псевдонима extern создает дополнительное пространство имен корневого уровня, которое является параллельным для глобального пространства имен (но не находится в его пределах).</span><span class="sxs-lookup"><span data-stu-id="6e497-111">Each extern alias declaration introduces an additional root-level namespace that parallels (but does not lie within) the global namespace.</span></span> <span data-ttu-id="6e497-112">Таким образом, на типы из каждой сборки можно ссылаться без неоднозначности, используя их полное имя, размещенное в соответствующем пространстве имен-псевдониме.</span><span class="sxs-lookup"><span data-stu-id="6e497-112">Thus types from each assembly can be referred to without ambiguity by using their fully qualified name, rooted in the appropriate namespace-alias.</span></span>  
  
 <span data-ttu-id="6e497-113">В предыдущем примере `GridV1::Grid` является элементом управления сетки из `grid.dll`, а `GridV2::Grid` — элементом управления сетки из `grid20.dll`.</span><span class="sxs-lookup"><span data-stu-id="6e497-113">In the previous example, `GridV1::Grid` would be the grid control from `grid.dll`, and `GridV2::Grid` would be the grid control from `grid20.dll`.</span></span>  
  
## <a name="using-visual-studio"></a><span data-ttu-id="6e497-114">Использование Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6e497-114">Using Visual Studio</span></span>

<span data-ttu-id="6e497-115">Если вы используете Visual Studio, псевдонимы можно указать аналогичным образом.</span><span class="sxs-lookup"><span data-stu-id="6e497-115">If you are using Visual Studio, aliases can be provided in similar way.</span></span>

<span data-ttu-id="6e497-116">Добавьте ссылку на *grid.dll* и *grid20.dll* в проект в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6e497-116">Add reference of *grid.dll* and *grid20.dll* to your project in Visual Studio.</span></span> <span data-ttu-id="6e497-117">Откройте вкладку свойств и измените псевдонимы с глобальных на GridV1 и GridV2 соответственно.</span><span class="sxs-lookup"><span data-stu-id="6e497-117">Open a property tab and change the Aliases from global to GridV1 and GridV2 respectively.</span></span>

<span data-ttu-id="6e497-118">Используйте эти псевдонимы так же, как описано выше.</span><span class="sxs-lookup"><span data-stu-id="6e497-118">Use these aliases the same way above</span></span>

```csharp
 extern alias GridV1;  
  
 extern alias GridV2;  
```

<span data-ttu-id="6e497-119">Теперь можно создать псевдоним для пространства имен или типа, *используя директиву псевдонимов using*.</span><span class="sxs-lookup"><span data-stu-id="6e497-119">Now you can create alias for a namespace or a type by *using alias directive*.</span></span> <span data-ttu-id="6e497-120">Дополнительные сведения см. в разделе [Директива using](using-directive.md).</span><span class="sxs-lookup"><span data-stu-id="6e497-120">For more information, see [using directive](using-directive.md).</span></span>

```csharp
using Class1V1 = GridV1::Namespace.Class1;

using Class1V2 = GridV2::Namespace.Class1;
```

## <a name="c-language-specification"></a><span data-ttu-id="6e497-121">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="6e497-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6e497-122">См. также</span><span class="sxs-lookup"><span data-stu-id="6e497-122">See also</span></span>

- [<span data-ttu-id="6e497-123">Справочник по C#</span><span class="sxs-lookup"><span data-stu-id="6e497-123">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="6e497-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6e497-124">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="6e497-125">Ключевые слова в C#</span><span class="sxs-lookup"><span data-stu-id="6e497-125">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="6e497-126">:: Оператор</span><span class="sxs-lookup"><span data-stu-id="6e497-126">:: Operator</span></span>](../operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="6e497-127">-reference (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="6e497-127">-reference (C# Compiler Options)</span></span>](../compiler-options/reference-compiler-option.md)
