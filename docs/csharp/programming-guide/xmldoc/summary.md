---
title: <summary> Руководство по программированию на C#.
description: Сведения о теге <summary> в XML, который используется для описания типа или элемента типа. Изучите примеры кода и ознакомьтесь с дополнительными ресурсами.
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: f9243e598aaf0c12dd48b48045f461b4b307c18f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380609"
---
# <a name="summary-c-programming-guide"></a><span data-ttu-id="7d8f4-105">\<summary> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="7d8f4-105">\<summary> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="7d8f4-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7d8f4-106">Syntax</span></span>

```xml
<summary>description</summary>
```

## <a name="parameters"></a><span data-ttu-id="7d8f4-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="7d8f4-107">Parameters</span></span>

- `description`

  <span data-ttu-id="7d8f4-108">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="7d8f4-108">A summary of the object.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d8f4-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="7d8f4-109">Remarks</span></span>

<span data-ttu-id="7d8f4-110">Тег `<summary>` следует использовать для описания типа или элемента типа.</span><span class="sxs-lookup"><span data-stu-id="7d8f4-110">The `<summary>` tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="7d8f4-111">Чтобы добавить дополнительную информацию в описание типа, используйте [\<remarks>](./remarks.md).</span><span class="sxs-lookup"><span data-stu-id="7d8f4-111">Use [\<remarks>](./remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="7d8f4-112">Чтобы включить средства документации, такие как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), для создания внутренних гиперссылок на страницы документации для элементов кода, используйте атрибут [cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="7d8f4-112">Use the [cref Attribute](./cref-attribute.md) to enable documentation tools such as [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>

<span data-ttu-id="7d8f4-113">Текст в теге `<summary>` является единственным источником сведений о типе для технологии IntelliSense и также отображается в окне обозревателя объектов.</span><span class="sxs-lookup"><span data-stu-id="7d8f4-113">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>

<span data-ttu-id="7d8f4-114">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="7d8f4-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="7d8f4-115">Для создания окончательной документации на основе сгенерированного компилятором файла можно создать пользовательское средство или применить такие средства, как [DocFX](https://dotnet.github.io/docfx/) или [Sandcastle](https://github.com/EWSoftware/SHFB).</span><span class="sxs-lookup"><span data-stu-id="7d8f4-115">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [DocFX](https://dotnet.github.io/docfx/) or [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>

## <a name="example"></a><span data-ttu-id="7d8f4-116">Пример</span><span class="sxs-lookup"><span data-stu-id="7d8f4-116">Example</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

<span data-ttu-id="7d8f4-117">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="7d8f4-117">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>YourNamespace</name>
    </assembly>
    <members>
        <member name="T:TestClass">
            text for class TestClass
        </member>
        <member name="M:TestClass.DoWork(System.Int32)">
            <summary>DoWork is a method in the TestClass class.
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>
            </summary>
            <seealso cref="M:TestClass.Main"/>
        </member>
        <member name="M:TestClass.Main">
            text for Main
        </member>
    </members>
</doc>
```

## <a name="example"></a><span data-ttu-id="7d8f4-118">Пример</span><span class="sxs-lookup"><span data-stu-id="7d8f4-118">Example</span></span>

<span data-ttu-id="7d8f4-119">В следующем примере показано, как создать ссылку `cref` на универсальный тип.</span><span class="sxs-lookup"><span data-stu-id="7d8f4-119">The following example shows how to make a `cref` reference to a generic type.</span></span>

[!code-csharp[csProgGuideDocComments#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#11)]

<span data-ttu-id="7d8f4-120">В предыдущем примере выводится следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="7d8f4-120">The previous example produces the following XML file.</span></span>

```xml
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:A">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:B">
            <summary cref="T:C`1">
            </summary>
        </member>
        <member name="T:C`1">
            <summary cref="T:A">
            </summary>
            <typeparam name="T"></typeparam>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="7d8f4-121">См. также</span><span class="sxs-lookup"><span data-stu-id="7d8f4-121">See also</span></span>

- [<span data-ttu-id="7d8f4-122">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="7d8f4-122">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="7d8f4-123">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="7d8f4-123">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
