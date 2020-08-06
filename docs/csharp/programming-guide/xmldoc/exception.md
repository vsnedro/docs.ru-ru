---
title: Руководство по программированию на C#. <exception>
description: Сведения о теге <exception> в XML. Этот тег позволяет указать, какие исключения могут быть созданы. Он может применяться к методам, свойствам, событиям и индексаторам.
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: 22a28f3fe6de5a0db9aea0f1fd7963d4e6fcee05
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381740"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="1bf33-104">\<exception> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="1bf33-104">\<exception> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1bf33-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1bf33-105">Syntax</span></span>

```xml
<exception cref="member">description</exception>
```

## <a name="parameters"></a><span data-ttu-id="1bf33-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="1bf33-106">Parameters</span></span>

- <span data-ttu-id="1bf33-107">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="1bf33-107">cref = " `member`"</span></span>

  <span data-ttu-id="1bf33-108">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="1bf33-108">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="1bf33-109">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="1bf33-109">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="1bf33-110">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="1bf33-110">`member` must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="1bf33-111">См. подробнее о том, как форматировать `member`, чтобы создать ссылку на универсальный тип, в руководстве по [обработке XML-файла](processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="1bf33-111">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>

- `description`

  <span data-ttu-id="1bf33-112">Описание исключения.</span><span class="sxs-lookup"><span data-stu-id="1bf33-112">A description of the exception.</span></span>

## <a name="remarks"></a><span data-ttu-id="1bf33-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="1bf33-113">Remarks</span></span>

<span data-ttu-id="1bf33-114">Тег `<exception>` служит для указания возможных исключений.</span><span class="sxs-lookup"><span data-stu-id="1bf33-114">The `<exception>` tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="1bf33-115">Этот тег может применяться к определениям методов, свойств, событий и индексаторов.</span><span class="sxs-lookup"><span data-stu-id="1bf33-115">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>

<span data-ttu-id="1bf33-116">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="1bf33-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

<span data-ttu-id="1bf33-117">Дополнительные сведения об обработке исключений см. в разделе [Исключения и обработка исключений](../exceptions/index.md).</span><span class="sxs-lookup"><span data-stu-id="1bf33-117">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="1bf33-118">Пример</span><span class="sxs-lookup"><span data-stu-id="1bf33-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]

## <a name="see-also"></a><span data-ttu-id="1bf33-119">См. также</span><span class="sxs-lookup"><span data-stu-id="1bf33-119">See also</span></span>

- [<span data-ttu-id="1bf33-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="1bf33-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="1bf33-121">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="1bf33-121">Recommended tags for documentation comments</span></span>](recommended-tags-for-documentation-comments.md)
