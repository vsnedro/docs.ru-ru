---
title: Руководство по программированию на C#. <see>
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
ms.openlocfilehash: 731e42a6d4d354b043a56dbe150bb03a693a9454
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/21/2020
ms.locfileid: "86863790"
---
# <a name="see-c-programming-guide"></a><span data-ttu-id="0c2a8-102">\<see> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="0c2a8-102">\<see> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="0c2a8-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0c2a8-103">Syntax</span></span>

```xml
<see cref="member"/>
```

## <a name="parameters"></a><span data-ttu-id="0c2a8-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="0c2a8-104">Parameters</span></span>

- <span data-ttu-id="0c2a8-105">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="0c2a8-105">cref = "`member`"</span></span>

  <span data-ttu-id="0c2a8-106">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="0c2a8-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="0c2a8-107">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="0c2a8-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="0c2a8-108">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="0c2a8-108">Place *member* within double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="0c2a8-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="0c2a8-109">Remarks</span></span>

<span data-ttu-id="0c2a8-110">Тег `<see>` позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="0c2a8-110">The `<see>` tag lets you specify a link from within text.</span></span> <span data-ttu-id="0c2a8-111">С помощью тега [\<seealso>](./seealso.md) можно указать, что текст должен быть размещен в разделе "См. также".</span><span class="sxs-lookup"><span data-stu-id="0c2a8-111">Use [\<seealso>](./seealso.md) to indicate that text should be placed in a See Also section.</span></span> <span data-ttu-id="0c2a8-112">Используйте [cref Attribute](./cref-attribute.md) для создания внутренних гиперссылок на страницы документации для элементов кода.</span><span class="sxs-lookup"><span data-stu-id="0c2a8-112">Use the [cref Attribute](./cref-attribute.md) to create internal hyperlinks to documentation pages for code elements.</span></span> <span data-ttu-id="0c2a8-113">Кроме того, ``href`` является допустимым атрибутом, который будет функционировать как гиперссылка.</span><span class="sxs-lookup"><span data-stu-id="0c2a8-113">Also, ``href`` is a valid Attribute that will function as a hyperlink.</span></span>

<span data-ttu-id="0c2a8-114">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="0c2a8-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="0c2a8-115">В следующем примере показан тег `<see>` в разделе сводки.</span><span class="sxs-lookup"><span data-stu-id="0c2a8-115">The following example shows a `<see>` tag within a summary section.</span></span>

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a><span data-ttu-id="0c2a8-116">См. также</span><span class="sxs-lookup"><span data-stu-id="0c2a8-116">See also</span></span>

- [<span data-ttu-id="0c2a8-117">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="0c2a8-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="0c2a8-118">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="0c2a8-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
