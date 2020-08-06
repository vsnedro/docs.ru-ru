---
title: Руководство по программированию на C#. <typeparamref>
description: Сведения о теге <typeparamref> в XML. Этот тег разрешает получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: a39e896f1242452c7bcc94faa1e7ef3086ae2149
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380726"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="08264-104">\<typeparamref> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="08264-104">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="08264-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="08264-105">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="08264-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="08264-106">Parameters</span></span>

- `name`

  <span data-ttu-id="08264-107">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="08264-107">The name of the type parameter.</span></span> <span data-ttu-id="08264-108">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="08264-108">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="08264-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="08264-109">Remarks</span></span>

<span data-ttu-id="08264-110">Дополнительные сведения о параметрах типа в универсальных типах и методах см. в разделе [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="08264-110">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="08264-111">Используйте этот тег, чтобы разрешить получателям файла документации форматировать слово определенным образом, например курсивным шрифтом.</span><span class="sxs-lookup"><span data-stu-id="08264-111">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="08264-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="08264-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="08264-113">Пример</span><span class="sxs-lookup"><span data-stu-id="08264-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="08264-114">См. также</span><span class="sxs-lookup"><span data-stu-id="08264-114">See also</span></span>

- [<span data-ttu-id="08264-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="08264-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="08264-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="08264-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
