---
title: <example> Руководство по программированию на C#.
description: Сведения о теге <example> в XML. Этот тег позволяет указать пример использования метода или другого элемента библиотеки.
ms.date: 07/20/2015
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C# XML tag
- example C# XML tag
ms.assetid: 32d6e73b-2554-4abb-83ee-a1e321334fd2
ms.openlocfilehash: dd529e8f2a54cf9086d0d8c555dd1adb70b99126
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381532"
---
# <a name="example-c-programming-guide"></a><span data-ttu-id="4f667-105">\<example> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4f667-105">\<example> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4f667-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f667-106">Syntax</span></span>

```xml
<example>description</example>
```

## <a name="parameters"></a><span data-ttu-id="4f667-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f667-107">Parameters</span></span>

- `description`

  <span data-ttu-id="4f667-108">Описание примера кода.</span><span class="sxs-lookup"><span data-stu-id="4f667-108">A description of the code sample.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f667-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f667-109">Remarks</span></span>

<span data-ttu-id="4f667-110">Тег `<example>` позволяет указать пример использования метода или другого элемента библиотеки.</span><span class="sxs-lookup"><span data-stu-id="4f667-110">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="4f667-111">Вместе с ним часто применяется тег [\<code>](./code.md).</span><span class="sxs-lookup"><span data-stu-id="4f667-111">This commonly involves using the [\<code>](./code.md) tag.</span></span>

<span data-ttu-id="4f667-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4f667-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4f667-113">Пример</span><span class="sxs-lookup"><span data-stu-id="4f667-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

## <a name="see-also"></a><span data-ttu-id="4f667-114">См. также</span><span class="sxs-lookup"><span data-stu-id="4f667-114">See also</span></span>

- [<span data-ttu-id="4f667-115">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4f667-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4f667-116">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="4f667-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
