---
title: <permission> Руководство по программированию на C#.
description: Узнайте о теге <permission> XML. Этот тег позволяет документировать доступ члена, а класс PermissionSet позволяет определить доступ к члену.
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: 38c87505b8b2973875e474ffd296dc02b7fb9de6
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381727"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="39a75-105">\<permission> (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="39a75-105">\<permission> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="39a75-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="39a75-106">Syntax</span></span>

```xml
<permission cref="member">description</permission>
```

## <a name="parameters"></a><span data-ttu-id="39a75-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="39a75-107">Parameters</span></span>

- <span data-ttu-id="39a75-108">cref = "`member`"</span><span class="sxs-lookup"><span data-stu-id="39a75-108">cref = " `member`"</span></span>

  <span data-ttu-id="39a75-109">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="39a75-109">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="39a75-110">Компилятор проверяет, существует ли элемент кода, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="39a75-110">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="39a75-111">*member* необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="39a75-111">*member* must appear within double quotation marks (" ").</span></span>

  <span data-ttu-id="39a75-112">Сведения о создании ссылки cref на универсальный тип см. в статье об [атрибуте cref](./cref-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="39a75-112">For information on how to create a cref reference to a generic type, see [cref attribute](./cref-attribute.md).</span></span>

- `description`

  <span data-ttu-id="39a75-113">Описание уровня доступа для члена.</span><span class="sxs-lookup"><span data-stu-id="39a75-113">A description of the access to the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="39a75-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="39a75-114">Remarks</span></span>

<span data-ttu-id="39a75-115">Тег `<permission>` позволяет документировать уровень доступа для элемента.</span><span class="sxs-lookup"><span data-stu-id="39a75-115">The `<permission>` tag lets you document the access of a member.</span></span> <span data-ttu-id="39a75-116">Задать уровень доступа для члена можно с помощью класса <xref:System.Security.PermissionSet>.</span><span class="sxs-lookup"><span data-stu-id="39a75-116">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>

<span data-ttu-id="39a75-117">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../language-reference/compiler-options/doc-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="39a75-117">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="39a75-118">Пример</span><span class="sxs-lookup"><span data-stu-id="39a75-118">Example</span></span>

[!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]

## <a name="see-also"></a><span data-ttu-id="39a75-119">См. также</span><span class="sxs-lookup"><span data-stu-id="39a75-119">See also</span></span>

- [<span data-ttu-id="39a75-120">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="39a75-120">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="39a75-121">Рекомендуемые теги для комментариев документации</span><span class="sxs-lookup"><span data-stu-id="39a75-121">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
