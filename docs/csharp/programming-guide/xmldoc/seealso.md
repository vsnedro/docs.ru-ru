---
title: <seealso> Руководство по программированию на C#.
description: Сведения об использовании тега <seealso> в XML. Этот тег позволяет указать текст, который должен отображаться в разделе "См. также".
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: e8618ef352a4fa7f0fd4c88733c6568b0e12e376
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380648"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="5bb39-105">\<seealso> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="5bb39-105">\<seealso> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="5bb39-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bb39-106">Syntax</span></span>

```xml
<seealso cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="5bb39-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bb39-107">Parameters</span></span>

- <span data-ttu-id="5bb39-108">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="5bb39-108">cref = " `member`"</span></span>

  <span data-ttu-id="5bb39-109">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="5bb39-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5bb39-110">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных. `member`</span><span class="sxs-lookup"><span data-stu-id="5bb39-110">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="5bb39-111">необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="5bb39-111">must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="5bb39-112">Сведения о создании ссылки cref на универсальный тип см. в статье об [атрибуте cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="5bb39-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

## <a name="remarks"></a><span data-ttu-id="5bb39-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="5bb39-113">Remarks</span></span>

<span data-ttu-id="5bb39-114">С помощью тега `<seealso>` можно указать текст, который должен отображаться в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="5bb39-114">The `<seealso>` tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="5bb39-115">Тег [\<see>](./see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="5bb39-115">Use [\<see>](./see.md) to specify a link from within text.</span></span>

<span data-ttu-id="5bb39-116">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="5bb39-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="5bb39-117">Пример</span><span class="sxs-lookup"><span data-stu-id="5bb39-117">Example</span></span>

<span data-ttu-id="5bb39-118">См. [\<summary>](./summary.md) с примером использования \<seealso>.</span><span class="sxs-lookup"><span data-stu-id="5bb39-118">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>

## <a name="see-also"></a><span data-ttu-id="5bb39-119">См. также</span><span class="sxs-lookup"><span data-stu-id="5bb39-119">See also</span></span>

- [<span data-ttu-id="5bb39-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="5bb39-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="5bb39-121">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="5bb39-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
