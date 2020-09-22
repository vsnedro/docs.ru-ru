---
title: Рекомендуемые XML-теги для комментариев документации
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 9f877ee3fc9d616dc1e946293489a8aab96ac2e1
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872798"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a><span data-ttu-id="59b40-102">Рекомендуется использовать XML-теги для комментариев документации (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="59b40-102">Recommended XML Tags for Documentation Comments (Visual Basic)</span></span>

<span data-ttu-id="59b40-103">Компилятор Visual Basic может обрабатывать комментарии документации в коде в XML-файле.</span><span class="sxs-lookup"><span data-stu-id="59b40-103">The Visual Basic compiler can process documentation comments in your code to an XML file.</span></span> <span data-ttu-id="59b40-104">Для обработки XML-файла в документации можно использовать дополнительные средства.</span><span class="sxs-lookup"><span data-stu-id="59b40-104">You can use additional tools to process the XML file into documentation.</span></span>  
  
 <span data-ttu-id="59b40-105">Комментарии XML разрешены в конструкциях кода, таких как типы и члены типов.</span><span class="sxs-lookup"><span data-stu-id="59b40-105">XML comments are allowed on code constructs such as types and type members.</span></span> <span data-ttu-id="59b40-106">Для разделяемых типов только одна часть типа может содержать комментарии XML, хотя не существует ограничений на комментирование его элементов.</span><span class="sxs-lookup"><span data-stu-id="59b40-106">For partial types, only one part of the type can have XML comments, although there is no restriction on commenting its members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59b40-107">Комментарии к документации нельзя применять к пространствам имен.</span><span class="sxs-lookup"><span data-stu-id="59b40-107">Documentation comments cannot be applied to namespaces.</span></span> <span data-ttu-id="59b40-108">Причина состоит в том, что одно пространство имен может охватывать несколько сборок, и не все сборки должны быть загружены одновременно.</span><span class="sxs-lookup"><span data-stu-id="59b40-108">The reason is that one namespace can span several assemblies, and not all assemblies have to be loaded at the same time.</span></span>  
  
 <span data-ttu-id="59b40-109">Компилятор обрабатывает любой тег, который является допустимым XML.</span><span class="sxs-lookup"><span data-stu-id="59b40-109">The compiler processes any tag that is valid XML.</span></span> <span data-ttu-id="59b40-110">Следующие теги предоставляют часто используемые функции в пользовательской документации.</span><span class="sxs-lookup"><span data-stu-id="59b40-110">The following tags provide commonly used functionality in user documentation.</span></span>  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|<span data-ttu-id="59b40-111">[\<exception>](exception.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="59b40-111">[\<exception>](exception.md) <sup>1</sup></span></span>|<span data-ttu-id="59b40-112">[\<include>](include.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="59b40-112">[\<include>](include.md) <sup>1</sup></span></span>|[\<list>](list.md)|  
|[\<para>](para.md)|<span data-ttu-id="59b40-113">[\<param>](param.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="59b40-113">[\<param>](param.md) <sup>1</sup></span></span>|[\<paramref>](paramref.md)|  
|<span data-ttu-id="59b40-114">[\<permission>](permission.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="59b40-114">[\<permission>](permission.md) <sup>1</sup></span></span>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|<span data-ttu-id="59b40-115">[\<see>](see.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="59b40-115">[\<see>](see.md) <sup>1</sup></span></span>|<span data-ttu-id="59b40-116">[\<seealso>](seealso.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="59b40-116">[\<seealso>](seealso.md) <sup>1</sup></span></span>|[\<summary>](summary.md)|  
|<span data-ttu-id="59b40-117">[\<typeparam>](typeparam.md)<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="59b40-117">[\<typeparam>](typeparam.md) <sup>1</sup></span></span>|[\<value>](value.md)||  
  
 <span data-ttu-id="59b40-118">(<sup>1</sup> компилятор проверяет синтаксис.)</span><span class="sxs-lookup"><span data-stu-id="59b40-118">(<sup>1</sup> The compiler verifies syntax.)</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59b40-119">Если необходимо, чтобы угловые скобки отображались в тексте комментария к документации, используйте `&lt;` и `&gt;` .</span><span class="sxs-lookup"><span data-stu-id="59b40-119">If you want angle brackets to appear in the text of a documentation comment, use `&lt;` and `&gt;`.</span></span> <span data-ttu-id="59b40-120">Например, строка `"&lt;text in angle brackets&gt;"` будет выглядеть так `<text in angle brackets>` :.</span><span class="sxs-lookup"><span data-stu-id="59b40-120">For example, the string `"&lt;text in angle brackets&gt;"` will appear as `<text in angle brackets>`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59b40-121">См. также</span><span class="sxs-lookup"><span data-stu-id="59b40-121">See also</span></span>

- [<span data-ttu-id="59b40-122">Документирование кода с помощью XML</span><span class="sxs-lookup"><span data-stu-id="59b40-122">Documenting Your Code with XML</span></span>](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="59b40-123">-doc</span><span class="sxs-lookup"><span data-stu-id="59b40-123">-doc</span></span>](../../reference/command-line-compiler/doc.md)
- [<span data-ttu-id="59b40-124">Практическое руководство. Создание XML-документации</span><span class="sxs-lookup"><span data-stu-id="59b40-124">How to: Create XML Documentation</span></span>](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
