---
title: Руководство по программированию на C#. Атрибут cref
description: Узнайте об атрибуте cref. Атрибут cref означает ссылку на код. Он указывает, что текст внутри тега представляет собой элемент кода.
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: 31fa1a3f182d7b72a1dfbe1ce47386f87fbbff75
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382000"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="791a1-104">Руководство по программированию на C#. Атрибут cref</span><span class="sxs-lookup"><span data-stu-id="791a1-104">cref attribute (C# programming guide)</span></span>

<span data-ttu-id="791a1-105">Атрибут `cref` в теге XML-документации означает "кодовая ссылка".</span><span class="sxs-lookup"><span data-stu-id="791a1-105">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="791a1-106">Он указывает, что текст внутри тега представляет собой элемент кода, например тип, метод или свойство.</span><span class="sxs-lookup"><span data-stu-id="791a1-106">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="791a1-107">Средства создания документации, такие как [DocFX](https://dotnet.github.io/docfx/) и [Sandcastle](https://github.com/EWSoftware/SHFB), используют атрибуты `cref` для автоматического создания гиперссылок на страницу, где документирован тип или член.</span><span class="sxs-lookup"><span data-stu-id="791a1-107">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>

## <a name="example"></a><span data-ttu-id="791a1-108">Пример</span><span class="sxs-lookup"><span data-stu-id="791a1-108">Example</span></span>

<span data-ttu-id="791a1-109">В следующем примере показаны атрибуты `cref`, используемые в тегах [\<see>](./see.md).</span><span class="sxs-lookup"><span data-stu-id="791a1-109">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

<span data-ttu-id="791a1-110">В результате компиляции программа создает следующий XML-файл.</span><span class="sxs-lookup"><span data-stu-id="791a1-110">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="791a1-111">Обратите внимание, что атрибут `cref` метода `GetZero`, в частности, был преобразован компилятором в `"M:TestNamespace.TestClass.GetZero"`.</span><span class="sxs-lookup"><span data-stu-id="791a1-111">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="791a1-112">Префикс "M:" означает "метод" и является условным обозначением, распознаваемым средствами документации, такими как DocFX и Sandcastle.</span><span class="sxs-lookup"><span data-stu-id="791a1-112">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="791a1-113">Полный список префиксов см. в разделе [Обработка XML-файла](./processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="791a1-113">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>

```xml  
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:TestNamespace.TestClass">
            <summary>
            TestClass contains several cref examples.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor">
            <summary>
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">
            <summary>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.GetZero">
            <summary>
            The GetZero method.
            </summary>
            <example>
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.
            <code>
            class TestClass
            {
                static int Main()
                {
                    return GetZero();
                }
            }
            </code>
            </example>
        </member>
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">
            <summary>
            The GetGenericValue method.
            </summary>
            <remarks>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.
            </remarks>
        </member>
        <member name="T:TestNamespace.GenericClass`1">
            <summary>
            GenericClass.
            </summary>
            <remarks>
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.
            </remarks>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="791a1-114">См. также</span><span class="sxs-lookup"><span data-stu-id="791a1-114">See also</span></span>

- [<span data-ttu-id="791a1-115">Комментарии XML-документации</span><span class="sxs-lookup"><span data-stu-id="791a1-115">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="791a1-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="791a1-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
