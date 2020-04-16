---
title: Встроенный тип XAML x:Code
ms.date: 03/30/2017
f1_keywords:
- Code
- x:Code
- xCode
helpviewer_keywords:
- Code directive in XAML [XAML Services]
- x:Code XAML directive element [XAML Services]
- XAML [XAML Services], x:Code directive element
ms.assetid: 87986b13-1a2e-4830-ae36-15f9dc5629e8
ms.openlocfilehash: 4da72ed630c1df001e3fd6c7e55f866b94c4d9b1
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432806"
---
# <a name="xcode-intrinsic-xaml-type"></a><span data-ttu-id="7ac53-102">Встроенный тип XAML x:Code</span><span class="sxs-lookup"><span data-stu-id="7ac53-102">x:Code Intrinsic XAML Type</span></span>
<span data-ttu-id="7ac53-103">Позволяет разместить код в рамках производства XAML.</span><span class="sxs-lookup"><span data-stu-id="7ac53-103">Allows placement of code within a XAML production.</span></span> <span data-ttu-id="7ac53-104">Такой код может быть компилирован любой реализацией процессора XAML, которая компилирует XAML, либо оставлен в производстве XAML для последующего использования, например, интерпретация времен выполнения.</span><span class="sxs-lookup"><span data-stu-id="7ac53-104">Such code can either be compiled by any XAML processor implementation that compiles XAML, or left in the XAML production for later uses such as interpretation by a runtime.</span></span>

## <a name="xaml-object-element-usage"></a><span data-ttu-id="7ac53-105">Использование элемента объекта XAML</span><span class="sxs-lookup"><span data-stu-id="7ac53-105">XAML Object Element Usage</span></span>

```xaml
<x:Code>
   // code instructions, usually enclosed by CDATA...
</x:Code>
```

## <a name="remarks"></a><span data-ttu-id="7ac53-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="7ac53-106">Remarks</span></span>

<span data-ttu-id="7ac53-107">Код в `x:Code` элементе директивы XAML по-прежнему интерпретируется в общем пространстве имен XML и предоставленных пространствах имен XAML.</span><span class="sxs-lookup"><span data-stu-id="7ac53-107">The code within the `x:Code` XAML directive element is still interpreted within the general XML namespace and the XAML namespaces provided.</span></span> <span data-ttu-id="7ac53-108">Поэтому обычно необходимо приложить код, используемый `x:Code` `CDATA` для внутри сегмента.</span><span class="sxs-lookup"><span data-stu-id="7ac53-108">Therefore, it is usually necessary to enclose the code used for `x:Code` inside a `CDATA` segment.</span></span>

<span data-ttu-id="7ac53-109">`x:Code`не допускается для всех возможных механизмов развертывания производства XAML.</span><span class="sxs-lookup"><span data-stu-id="7ac53-109">`x:Code` is not permitted for all possible deployment mechanisms of a XAML production.</span></span> <span data-ttu-id="7ac53-110">В конкретных рамках (например, WPF) код должен быть скомпилирован.</span><span class="sxs-lookup"><span data-stu-id="7ac53-110">In specific frameworks (for example WPF) the code must be compiled.</span></span> <span data-ttu-id="7ac53-111">В других средах `x:Code` использование может быть обычно запрещено.</span><span class="sxs-lookup"><span data-stu-id="7ac53-111">In other frameworks, `x:Code` usage might be generally disallowed.</span></span>

<span data-ttu-id="7ac53-112">Для инфраструктур, позволяющих управлять `x:Code` контентом, правильный `x:Code` компилятор языка для использования в контенте определяется настройками и целями содержащегося проекта, который используется для компиляции приложения.</span><span class="sxs-lookup"><span data-stu-id="7ac53-112">For frameworks that permit managed `x:Code` content, the correct language compiler to use for `x:Code` content is determined by settings and targets of the containing project that is used to compile the application.</span></span>

## <a name="wpf-usage-notes"></a><span data-ttu-id="7ac53-113">Примечания об использовании WPF</span><span class="sxs-lookup"><span data-stu-id="7ac53-113">WPF Usage Notes</span></span>

<span data-ttu-id="7ac53-114">Код, `x:Code` декларированный в рамках для WPF, имеет несколько заметных ограничений:</span><span class="sxs-lookup"><span data-stu-id="7ac53-114">Code declared within `x:Code` for WPF has several notable limitations:</span></span>

- <span data-ttu-id="7ac53-115">Элемент `x:Code` директивы должен быть непосредственным элементом ребенка корневого элемента производства XAML.</span><span class="sxs-lookup"><span data-stu-id="7ac53-115">The `x:Code` directive element must be an immediate child element of the root element of the XAML production.</span></span>

- <span data-ttu-id="7ac53-116">[x: Директива класса](xclass-directive.md) должна быть предоставлена на элементе родительского корневого элемента.</span><span class="sxs-lookup"><span data-stu-id="7ac53-116">[x:Class Directive](xclass-directive.md) must be provided on the parent root element.</span></span>

- <span data-ttu-id="7ac53-117">Код, размещенный внутри, `x:Code` будет обрабатываться компиляцией, которая будет находиться в рамках частичный класс, который уже создается для этой страницы XAML.</span><span class="sxs-lookup"><span data-stu-id="7ac53-117">The code placed within `x:Code` will be treated by compilation to be within the scope of the partial class that is already being created for that XAML page.</span></span> <span data-ttu-id="7ac53-118">Поэтому весь код, который вы определяете, должен быть членами или переменными этого частичного класса.</span><span class="sxs-lookup"><span data-stu-id="7ac53-118">Therefore all code you define must be members or variables of that partial class.</span></span>

- <span data-ttu-id="7ac53-119">Нельзя определить дополнительные классы, кроме как вложения класса внутри частичного класса (гнездо разрешено, но это не типично, поскольку вложенные классы не могут быть отнесены к XAML).</span><span class="sxs-lookup"><span data-stu-id="7ac53-119">You cannot define additional classes, other than by nesting a class inside the partial class (nesting is allowed, but it is not typical because nested classes cannot be referenced in XAML).</span></span> <span data-ttu-id="7ac53-120">Пространства имен CLR, отличные от пространства имен, используемого для существующего частичного класса, не могут быть определены или добавлены.</span><span class="sxs-lookup"><span data-stu-id="7ac53-120">CLR namespaces other than the namespace that is used for the existing partial class cannot be defined or added to.</span></span>

- <span data-ttu-id="7ac53-121">Ссылки на кодовые сущности за пределами частичного пространства имен класса CLR должны быть полностью квалифицированы.</span><span class="sxs-lookup"><span data-stu-id="7ac53-121">References to code entities outside the partial class CLR namespace must all be fully qualified.</span></span> <span data-ttu-id="7ac53-122">Если объявленные участники переопределяются с частичным классом, которые перекрываются, это должно быть указано с помощью ключевого слова, конкретного языка переопределения.</span><span class="sxs-lookup"><span data-stu-id="7ac53-122">If members being declared are overrides to the partial class overridable members, this must be specified with the language-specific override keyword.</span></span> <span data-ttu-id="7ac53-123">Если участники `x:Code` объявили в сфере конфликта с членами частичного класса, созданными из XAML, таким образом, что компилятор сообщает о конфликте, файл XAML не может компилировать или загружать.</span><span class="sxs-lookup"><span data-stu-id="7ac53-123">If members declared in `x:Code` scope conflict with members of the partial class created out of the XAML, in such a way that the compiler reports the conflict, the XAML file cannot compile or load.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ac53-124">См. также</span><span class="sxs-lookup"><span data-stu-id="7ac53-124">See also</span></span>

- [<span data-ttu-id="7ac53-125">Директива x:Class</span><span class="sxs-lookup"><span data-stu-id="7ac53-125">x:Class Directive</span></span>](xclass-directive.md)
- [<span data-ttu-id="7ac53-126">Код программной части и XAML в WPF</span><span class="sxs-lookup"><span data-stu-id="7ac53-126">Code-Behind and XAML in WPF</span></span>](../../framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [<span data-ttu-id="7ac53-127">Обзор XAML (WPF)</span><span class="sxs-lookup"><span data-stu-id="7ac53-127">XAML Overview (WPF)</span></span>](../fundamentals/xaml.md)
