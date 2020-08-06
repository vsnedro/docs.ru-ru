---
title: <returns> Руководство по программированию на C#.
description: Сведения о теге <returns> в XML. Этот тег используется в комментариях к объявлению метода для описания возвращаемого значения.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: e461d46df619a351048ae7942e59847d39e490f9
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381402"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="ff893-105">\<returns> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="ff893-105">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="ff893-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff893-106">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="ff893-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ff893-107">Parameters</span></span>

- `description`

  <span data-ttu-id="ff893-108">Описание возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="ff893-108">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="ff893-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="ff893-109">Remarks</span></span>

<span data-ttu-id="ff893-110">Тег `<returns>` следует использовать в комментариях к объявлению метода для описания возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="ff893-110">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="ff893-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ff893-111">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="ff893-112">Пример</span><span class="sxs-lookup"><span data-stu-id="ff893-112">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="ff893-113">См. также</span><span class="sxs-lookup"><span data-stu-id="ff893-113">See also</span></span>

- [<span data-ttu-id="ff893-114">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="ff893-114">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="ff893-115">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="ff893-115">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
