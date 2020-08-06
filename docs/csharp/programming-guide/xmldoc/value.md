---
title: <value> Руководство по программированию на C#.
description: Сведения о теге <value> в XML. Этот тег позволяет описать значение, которое представляется свойством.
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: d8294b477d7067653c71d1ec2047a85a0bfe6d02
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87380778"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="04d84-105">\<value> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="04d84-105">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="04d84-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04d84-106">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="04d84-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="04d84-107">Parameters</span></span>

- `property-description`

  <span data-ttu-id="04d84-108">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="04d84-108">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="04d84-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="04d84-109">Remarks</span></span>

<span data-ttu-id="04d84-110">Тег `<value>` позволяет описывать значение, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="04d84-110">The `<value>` tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="04d84-111">При добавлении свойства с помощью мастера создания кода из среды разработки Visual Studio .NET для нового свойства будет добавлен тег [\<summary>](./summary.md).</span><span class="sxs-lookup"><span data-stu-id="04d84-111">When you add a property via code wizard in the Visual Studio .NET development environment, it adds a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="04d84-112">После этого следует вручную добавить тег `<value>` для описания значения, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="04d84-112">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>

<span data-ttu-id="04d84-113">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="04d84-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="04d84-114">Пример</span><span class="sxs-lookup"><span data-stu-id="04d84-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="04d84-115">См. также</span><span class="sxs-lookup"><span data-stu-id="04d84-115">See also</span></span>

- [<span data-ttu-id="04d84-116">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="04d84-116">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="04d84-117">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="04d84-117">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
