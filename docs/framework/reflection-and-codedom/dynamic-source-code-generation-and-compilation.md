---
title: Динамическое создание и компиляция исходного кода
description: Скомпилируйте и создайте динамический исходный код в .NET с помощью Code Document Object Model (CodeDOM). Элементы CodeDOM связаны друг с другом для формирования графа CodeDOM.
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
ms.openlocfilehash: 3cdd89ac9745f6af133ca683afff64283f2727d1
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475103"
---
# <a name="compile-and-generate-dynamic-source-code"></a><span data-ttu-id="a528b-104">Компиляция и создание динамического исходного кода</span><span class="sxs-lookup"><span data-stu-id="a528b-104">Compile and generate dynamic source code</span></span>

<span data-ttu-id="a528b-105">В среду .NET Framework включен механизм, который называется Code Document Object Model (CodeDOM). Он позволяет разработчикам программ, порождающих исходный код, создавать код на нескольких языках программирования во время выполнения на основе единой модели, представляющей код для визуализации.</span><span class="sxs-lookup"><span data-stu-id="a528b-105">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
<span data-ttu-id="a528b-106">Для представления исходного кода элементы CodeDOM связываются друг с другом, образуя структуру данных, известную как граф CodeDOM, которая моделирует структуру некоторого исходного кода.</span><span class="sxs-lookup"><span data-stu-id="a528b-106">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
<span data-ttu-id="a528b-107">Пространство имен <xref:System.CodeDom?displayProperty=fullName> определяет типы, с помощью которых логическая структура исходного кода может быть представлена независимо от конкретного языка программирования.</span><span class="sxs-lookup"><span data-stu-id="a528b-107">The <xref:System.CodeDom?displayProperty=fullName> namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="a528b-108">Пространство имен <xref:System.CodeDom.Compiler?displayProperty=fullName> определяет типы, используемые для формирования исходного кода на основе графов CodeDOM и управления компиляцией исходного кода на поддерживаемых языках.</span><span class="sxs-lookup"><span data-stu-id="a528b-108">The <xref:System.CodeDom.Compiler?displayProperty=fullName> namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="a528b-109">Набор поддерживаемых языков может быть расширен разработчиками или поставщиками компиляторов.</span><span class="sxs-lookup"><span data-stu-id="a528b-109">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
<span data-ttu-id="a528b-110">Независимое от языка моделирование исходного кода может быть полезно, если программа должна создавать исходный код для модели программы на нескольких языках или если конечный язык заранее не определен.</span><span class="sxs-lookup"><span data-stu-id="a528b-110">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="a528b-111">Например, некоторые конструкторы используют модель CodeDOM в качестве интерфейса абстракции от языка для получения исходного кода на требуемом языке программирования, если имеется поддержка CodeDOM для этого языка.</span><span class="sxs-lookup"><span data-stu-id="a528b-111">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
<span data-ttu-id="a528b-112">В платформе .NET Framework имеются генераторы и компиляторы кода для языков <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> и <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="a528b-112">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a528b-113">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="a528b-113">In this section</span></span>

- [<span data-ttu-id="a528b-114">Использование CodeDOM</span><span class="sxs-lookup"><span data-stu-id="a528b-114">Using the CodeDOM</span></span>](using-the-codedom.md)

  <span data-ttu-id="a528b-115">Описываются общие случаи применения, а также демонстрируется создание простого графа объектов с использованием CodeDOM.</span><span class="sxs-lookup"><span data-stu-id="a528b-115">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
- [<span data-ttu-id="a528b-116">Создание исходного кода и компиляция программы из графа CodeDOM</span><span class="sxs-lookup"><span data-stu-id="a528b-116">Generate Source Code and Compile a Program from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)  

  <span data-ttu-id="a528b-117">Описание способов формирования исходного кода и его компиляции внешним компилятором с использованием классов, определенных в пространстве имен `System.CodeDom.Compiler`.</span><span class="sxs-lookup"><span data-stu-id="a528b-117">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
- [<span data-ttu-id="a528b-118">Практическое руководство. Создание XML-файла документации с использованием CodeDOM</span><span class="sxs-lookup"><span data-stu-id="a528b-118">How to: Create an XML Documentation File Using CodeDOM</span></span>](how-to-create-an-xml-documentation-file-using-codedom.md)  

  <span data-ttu-id="a528b-119">Описание использования CodeDOM для формирования кода с комментариями к XML-документации и компиляции сформированного кода для создания XML-документации.</span><span class="sxs-lookup"><span data-stu-id="a528b-119">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
- [<span data-ttu-id="a528b-120">Практическое руководство. Создание класса с помощью CodeDOM</span><span class="sxs-lookup"><span data-stu-id="a528b-120">How to: Create a Class Using CodeDOM</span></span>](how-to-create-a-class-using-codedom.md)  

  <span data-ttu-id="a528b-121">Описание использования CodeDOM для создания класса, содержащего поля, свойства, метод, конструктор и точку входа.</span><span class="sxs-lookup"><span data-stu-id="a528b-121">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a528b-122">Справочник</span><span class="sxs-lookup"><span data-stu-id="a528b-122">Reference</span></span>  

- <xref:System.CodeDom>  

  <span data-ttu-id="a528b-123">Определяет элементы, представляющие элементы кода на языках программирования, предназначенных для среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a528b-123">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
- <xref:System.CodeDom.Compiler>  

  <span data-ttu-id="a528b-124">Определяет интерфейсы для формирования и компиляции кода во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="a528b-124">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a528b-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="a528b-125">Related sections</span></span>  

- <span data-ttu-id="a528b-126">[Краткий справочник по CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) — здесь разработчики могут быстро найти элементы CodeDOM, представляющие элементы исходного кода.</span><span class="sxs-lookup"><span data-stu-id="a528b-126">[CodeDOM Quick Reference](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100)) provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
