---
title: Руководство по программированию на C#. Комментарии XML-документации
description: Сведения о комментариях XML-документации. Вы можете создавать документацию для кода, включив XML-элементы в специальные поля комментариев.
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: fbdeb53331d9fc63d24a3322ea13863d7c0a3630
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381883"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="7ab19-104">Руководство по программированию на C#. Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="7ab19-104">XML documentation comments (C# programming guide)</span></span>

<span data-ttu-id="7ab19-105">В C# можно создавать документацию для кода путем включения XML-элементов в специальные поля комментариев (начинающиеся с трех символов косой черты) в исходном коде непосредственно перед блоком кода, к которому относятся комментарии. Например:</span><span class="sxs-lookup"><span data-stu-id="7ab19-105">In C#, you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example.</span></span>

```csharp
/// <summary>
///  This class performs an important function.
/// </summary>
public class MyClass {}
```

<span data-ttu-id="7ab19-106">При выполнении компиляции с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md) компилятор осуществляет поиск всех тегов XML в исходном коде и создает XML-файл документации.</span><span class="sxs-lookup"><span data-stu-id="7ab19-106">When you compile with the [-doc](../../language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="7ab19-107">Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="7ab19-107">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

<span data-ttu-id="7ab19-108">Для ссылки на XML-элементы (например, если функция обрабатывает определенные XML-элементы, которые требуется включить в комментарии XML-документации) можно использовать стандартный механизм заключения в скобки (`<` и `>`).</span><span class="sxs-lookup"><span data-stu-id="7ab19-108">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="7ab19-109">Для ссылки на универсальные идентификаторы в элементах ссылок кода (`cref`) можно использовать escape-символы (например, `cref="List&lt;T&gt;"`) или фигурные скобки (`cref="List{T}"`).</span><span class="sxs-lookup"><span data-stu-id="7ab19-109">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="7ab19-110">В особом случае компилятор анализирует фигурные скобки, как угловые, чтобы при ссылке на универсальные идентификаторы сделать комментарий документации менее громоздким.</span><span class="sxs-lookup"><span data-stu-id="7ab19-110">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>

> [!NOTE]
> <span data-ttu-id="7ab19-111">Комментарии XML-документации не являются метаданными. Они не включаются в скомпилированную сборку, и поэтому не доступны посредством отражения.</span><span class="sxs-lookup"><span data-stu-id="7ab19-111">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7ab19-112">Содержание раздела</span><span class="sxs-lookup"><span data-stu-id="7ab19-112">In this section</span></span>

- [<span data-ttu-id="7ab19-113">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="7ab19-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)

- [<span data-ttu-id="7ab19-114">Обработка XML-файла</span><span class="sxs-lookup"><span data-stu-id="7ab19-114">Processing the XML file</span></span>](./processing-the-xml-file.md)

- [<span data-ttu-id="7ab19-115">Разделители для тегов документации</span><span class="sxs-lookup"><span data-stu-id="7ab19-115">Delimiters for documentation tags</span></span>](./delimiters-for-documentation-tags.md)

- [<span data-ttu-id="7ab19-116">Практическое руководство. Использование XML-документации</span><span class="sxs-lookup"><span data-stu-id="7ab19-116">How to use the XML documentation features</span></span>](./how-to-use-the-xml-documentation-features.md)

## <a name="related-sections"></a><span data-ttu-id="7ab19-117">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7ab19-117">Related sections</span></span>

<span data-ttu-id="7ab19-118">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="7ab19-118">For more information, see:</span></span>

- [<span data-ttu-id="7ab19-119">-doc (обработка комментариев документации)</span><span class="sxs-lookup"><span data-stu-id="7ab19-119">-doc (Process Documentation Comments)</span></span>](../../language-reference/compiler-options/doc-compiler-option.md)

## <a name="c-language-specification"></a><span data-ttu-id="7ab19-120">Спецификация языка C#</span><span class="sxs-lookup"><span data-stu-id="7ab19-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7ab19-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7ab19-121">See also</span></span>

- [<span data-ttu-id="7ab19-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7ab19-122">C# Programming Guide</span></span>](../index.md)
