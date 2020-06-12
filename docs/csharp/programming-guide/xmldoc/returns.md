---
title: <returns> Руководство по программированию на C#.
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 7bc950a8d89a3ac2b5c3b7a68e05c7778e97f85c
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287237"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="00e27-102">\<returns> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="00e27-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="00e27-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00e27-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="00e27-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="00e27-104">Parameters</span></span>

- `description`

  <span data-ttu-id="00e27-105">Описание возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="00e27-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="00e27-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="00e27-106">Remarks</span></span>

<span data-ttu-id="00e27-107">Тег `<returns>` следует использовать в комментариях к объявлению метода для описания возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="00e27-107">The `<returns>` tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="00e27-108">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="00e27-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="00e27-109">Пример</span><span class="sxs-lookup"><span data-stu-id="00e27-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="00e27-110">См. также</span><span class="sxs-lookup"><span data-stu-id="00e27-110">See also</span></span>

- [<span data-ttu-id="00e27-111">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="00e27-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="00e27-112">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="00e27-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
