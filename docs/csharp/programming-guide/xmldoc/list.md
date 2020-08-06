---
title: <list> Руководство по программированию на C#.
description: Сведения о теге <list> XML. Этот тег используется для создания таблиц и определений, маркированных или нумерованных списков с помощью блоков item.
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: 361c2e6f343554a9b8519c3b2e41219b209e682d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381870"
---
# <a name="list-c-programming-guide"></a><span data-ttu-id="e35f2-105">\<list> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="e35f2-105">\<list> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="e35f2-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e35f2-106">Syntax</span></span>

```xml
<list type="bullet|number|table">
    <listheader>
        <term>term</term>
        <description>description</description>
    </listheader>
    <item>
        <term>term</term>
        <description>description</description>
    </item>
</list>
```

## <a name="parameters"></a><span data-ttu-id="e35f2-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="e35f2-107">Parameters</span></span>

- `term`

  <span data-ttu-id="e35f2-108">Термин, который будет определен в `description`.</span><span class="sxs-lookup"><span data-stu-id="e35f2-108">A term to define, which will be defined in `description`.</span></span>

- `description`

  <span data-ttu-id="e35f2-109">Либо элемент маркированного или нумерованного списка, либо определение `term`.</span><span class="sxs-lookup"><span data-stu-id="e35f2-109">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e35f2-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="e35f2-110">Remarks</span></span>

<span data-ttu-id="e35f2-111">Блок `<listheader>` используется для определения строки заголовка в таблице или списке определений.</span><span class="sxs-lookup"><span data-stu-id="e35f2-111">The `<listheader>` block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="e35f2-112">При определении таблицы необходимо ввести данные для термина в заголовке.</span><span class="sxs-lookup"><span data-stu-id="e35f2-112">When defining a table, you only need to supply an entry for term in the heading.</span></span>

<span data-ttu-id="e35f2-113">Каждый элемент в списке указывается в блоке `<item>`.</span><span class="sxs-lookup"><span data-stu-id="e35f2-113">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="e35f2-114">При создании списка определений необходимо указать одновременно `term` и `description`.</span><span class="sxs-lookup"><span data-stu-id="e35f2-114">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="e35f2-115">Тем не менее для таблицы, маркированного или нумерованного списка достаточно ввести только `description`.</span><span class="sxs-lookup"><span data-stu-id="e35f2-115">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>

<span data-ttu-id="e35f2-116">Число блоков `<item>` в списке или таблице не ограничено.</span><span class="sxs-lookup"><span data-stu-id="e35f2-116">A list or table can have as many `<item>` blocks as needed.</span></span>

<span data-ttu-id="e35f2-117">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="e35f2-117">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="e35f2-118">Пример</span><span class="sxs-lookup"><span data-stu-id="e35f2-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#6)]

## <a name="see-also"></a><span data-ttu-id="e35f2-119">См. также</span><span class="sxs-lookup"><span data-stu-id="e35f2-119">See also</span></span>

- [<span data-ttu-id="e35f2-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="e35f2-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="e35f2-121">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="e35f2-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
