---
title: <typeparam> Руководство по программированию на C#.
description: Сведения о теге <typeparam> в XML. Этот тег используется в комментариях к объявлению универсального типа или метода для описания параметра типа.
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 5e5333e384e8c77b500f74ab7c6038146df6e2c0
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380791"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="4a738-105">\<typeparam> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="4a738-105">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="4a738-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4a738-106">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="4a738-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="4a738-107">Parameters</span></span>

- `name`

  <span data-ttu-id="4a738-108">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="4a738-108">The name of the type parameter.</span></span> <span data-ttu-id="4a738-109">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="4a738-109">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="4a738-110">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="4a738-110">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="4a738-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="4a738-111">Remarks</span></span>

<span data-ttu-id="4a738-112">Тег `<typeparam>` следует использовать в комментариях к объявлению универсального типа или метода для описания параметра типа.</span><span class="sxs-lookup"><span data-stu-id="4a738-112">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="4a738-113">Добавьте такой тег для каждого параметра типа универсального типа или метода.</span><span class="sxs-lookup"><span data-stu-id="4a738-113">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="4a738-114">Дополнительные сведения см. в статье [Универсальные шаблоны](../generics/index.md).</span><span class="sxs-lookup"><span data-stu-id="4a738-114">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="4a738-115">Текст тега `<typeparam>` будет отображаться в IntelliSense, (веб-отчет по комментариям к коду в [окне обозревателя объектов](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)).</span><span class="sxs-lookup"><span data-stu-id="4a738-115">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="4a738-116">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="4a738-116">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="4a738-117">Пример</span><span class="sxs-lookup"><span data-stu-id="4a738-117">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="4a738-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4a738-118">See also</span></span>

- [<span data-ttu-id="4a738-119">справочник по C#</span><span class="sxs-lookup"><span data-stu-id="4a738-119">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="4a738-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="4a738-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="4a738-121">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="4a738-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
