---
title: Руководство по программированию на C#. <see>
description: Сведения о теге <see> в XML. Этот тег позволяет указать ссылку в тексте, например с помощью атрибута cref.
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 1cc4982d1ebe9d6896404218a6d200b10cc6503f
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381935"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="26186-104">\<see> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="26186-104">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="26186-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="26186-105">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="26186-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="26186-106">Parameters</span></span>

- <span data-ttu-id="26186-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="26186-107">cref = "`member`"</span></span>

  <span data-ttu-id="26186-108">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="26186-108">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="26186-109">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="26186-109">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="26186-110">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="26186-110">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="26186-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="26186-111">Remarks</span></span>

<span data-ttu-id="26186-112">Тег `<see>` позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="26186-112">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="26186-113">С помощью тега [\<seealso>](./seealso.md) можно указать, что текст должен быть размещен в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="26186-113">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="26186-114">Используйте [cref Attribute](./cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода.</span><span class="sxs-lookup"><span data-stu-id="26186-114">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span> <span data-ttu-id="26186-115">Кроме того, ``href`` является допустимым атрибутом, который будет функционировать как гиперссылка.</span><span class="sxs-lookup"><span data-stu-id="26186-115">Also, ``href`` is a valid Attribute that will function as a hyperlink.</span></span>

<span data-ttu-id="26186-116">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="26186-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="26186-117">В следующем примере показан тег `<see>` в разделе сводки.</span><span class="sxs-lookup"><span data-stu-id="26186-117">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="26186-118">См. также</span><span class="sxs-lookup"><span data-stu-id="26186-118">See also</span></span>

- [<span data-ttu-id="26186-119">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="26186-119">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="26186-120">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="26186-120">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
