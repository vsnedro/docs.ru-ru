---
title: Руководство по программированию на C#. <c>
description: Сведения о теге <c> в XML. С помощью этого тега можно пометить однострочный текст в описании как код, если код <code> представлен несколькими строкамиindicates multiple lines..
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: 78e59e1df4b096782e0a97b6d12c21c843a1cb21
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382026"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="a07d0-104">\<c> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="a07d0-104">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="a07d0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a07d0-105">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="a07d0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a07d0-106">Parameters</span></span>

- `text`

  <span data-ttu-id="a07d0-107">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="a07d0-107">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="a07d0-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="a07d0-108">Remarks</span></span>

<span data-ttu-id="a07d0-109">С помощью тега `<c>` можно указать, что текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="a07d0-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="a07d0-110">Чтобы определить несколько строк в качестве кода, используйте тег [\<code>](./code.md).</span><span class="sxs-lookup"><span data-stu-id="a07d0-110">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="a07d0-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a07d0-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="a07d0-112">Пример</span><span class="sxs-lookup"><span data-stu-id="a07d0-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="a07d0-113">См. также</span><span class="sxs-lookup"><span data-stu-id="a07d0-113">See also</span></span>

- [<span data-ttu-id="a07d0-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="a07d0-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="a07d0-115">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="a07d0-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
