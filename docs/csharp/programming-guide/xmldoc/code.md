---
title: <code> - C# programming guide
description: Сведения о <code> tag. This tag is used to indicate multiple lines of code, while <c> marks single-line text in a description as code. в XML.
ms.date: 07/20/2015
f1_keywords:
- code
- <code>
helpviewer_keywords:
- code XML tag
- <code> C# XML tag
ms.assetid: f235e3bc-a709-43cf-8a9f-bd57cabdf6da
ms.openlocfilehash: f1f4cd930a876c8eca13de5f015e2b42b928d6f1
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87382013"
---
# <a name="code-c-programming-guide"></a><span data-ttu-id="c16ee-102">\<code> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="c16ee-102">\<code> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="c16ee-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c16ee-103">Syntax</span></span>

```xml
<code>content</code>
```

## <a name="parameters"></a><span data-ttu-id="c16ee-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="c16ee-104">Parameters</span></span>

- `content`

  <span data-ttu-id="c16ee-105">Текст, который необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="c16ee-105">The text you want marked as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="c16ee-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="c16ee-106">Remarks</span></span>

<span data-ttu-id="c16ee-107">Тег `<code>` используется для указания нескольких строк кода.</span><span class="sxs-lookup"><span data-stu-id="c16ee-107">The `<code>` tag is used to indicate multiple lines of code.</span></span> <span data-ttu-id="c16ee-108">С помощью тега [\<c>](./code-inline.md) можно указать, что однострочный текст в описании необходимо пометить как код.</span><span class="sxs-lookup"><span data-stu-id="c16ee-108">Use [\<c>](./code-inline.md) to indicate that single-line text within a description should be marked as code.</span></span>

<span data-ttu-id="c16ee-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="c16ee-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="c16ee-110">Пример</span><span class="sxs-lookup"><span data-stu-id="c16ee-110">Example</span></span>

<span data-ttu-id="c16ee-111">Пример использования тега `<code>` см. в статье [\<example>](./example.md).</span><span class="sxs-lookup"><span data-stu-id="c16ee-111">See the [\<example>](./example.md) article for an example of how to use the `<code>` tag.</span></span>

## <a name="see-also"></a><span data-ttu-id="c16ee-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c16ee-112">See also</span></span>

- [<span data-ttu-id="c16ee-113">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="c16ee-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="c16ee-114">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="c16ee-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
