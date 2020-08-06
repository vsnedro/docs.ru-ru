---
title: <para> Руководство по программированию на C#.
description: Сведения о теге <para> в XML. Этот тег позволяет добавить структуру к тексту в другом теге, например <summary>, <remarks>или <returns>.
ms.date: 07/20/2015
f1_keywords:
- <para>
- para
helpviewer_keywords:
- <para> C# XML tag
- para C# XML tag
ms.assetid: c74b8705-29df-40b1-bff5-237492b0e978
ms.openlocfilehash: 146078bcb556b4085724ddcdac561ea868ab0481
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381857"
---
# <a name="para-c-programming-guide"></a><span data-ttu-id="69980-108">\<para> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="69980-108">\<para> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="69980-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="69980-109">Syntax</span></span>

```xml
<para>content</para>
```

## <a name="parameters"></a><span data-ttu-id="69980-110">Параметры</span><span class="sxs-lookup"><span data-stu-id="69980-110">Parameters</span></span>

- `content`

  <span data-ttu-id="69980-111">Текст абзаца.</span><span class="sxs-lookup"><span data-stu-id="69980-111">The text of the paragraph.</span></span>

## <a name="remarks"></a><span data-ttu-id="69980-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="69980-112">Remarks</span></span>

<span data-ttu-id="69980-113">Тег `<para>` используется внутри другого тега, например [\<summary>](./summary.md), [\<remarks>](./remarks.md) или [\<returns>](./returns.md), и позволяет добавить к тексту структуру.</span><span class="sxs-lookup"><span data-stu-id="69980-113">The `<para>` tag is for use inside a tag, such as [\<summary>](./summary.md), [\<remarks>](./remarks.md), or [\<returns>](./returns.md), and lets you add structure to the text.</span></span>

<span data-ttu-id="69980-114">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="69980-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="69980-115">Пример</span><span class="sxs-lookup"><span data-stu-id="69980-115">Example</span></span>

<span data-ttu-id="69980-116">См. [\<summary>](./summary.md) с примером использования `<para>`.</span><span class="sxs-lookup"><span data-stu-id="69980-116">See [\<summary>](./summary.md) for an example of using `<para>`.</span></span>

## <a name="see-also"></a><span data-ttu-id="69980-117">См. также</span><span class="sxs-lookup"><span data-stu-id="69980-117">See also</span></span>

- [<span data-ttu-id="69980-118">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="69980-118">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="69980-119">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="69980-119">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
