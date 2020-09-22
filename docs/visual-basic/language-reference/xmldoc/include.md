---
title: <include>
ms.date: 07/20/2015
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
ms.openlocfilehash: df8749ca9d6c92cf9ef95f03eea2704812ff495a
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872876"
---
# <a name="include-visual-basic"></a><span data-ttu-id="cbff2-101">\<include> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cbff2-101">\<include> (Visual Basic)</span></span>

<span data-ttu-id="cbff2-102">Ссылается на другой файл, описывающий типы и члены в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="cbff2-102">Refers to another file that describes the types and members in your source code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbff2-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cbff2-103">Syntax</span></span>  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbff2-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="cbff2-104">Parameters</span></span>  

 `filename`  
 <span data-ttu-id="cbff2-105">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="cbff2-105">Required.</span></span> <span data-ttu-id="cbff2-106">Имя файла, содержащего документацию.</span><span class="sxs-lookup"><span data-stu-id="cbff2-106">The name of the file containing the documentation.</span></span> <span data-ttu-id="cbff2-107">Имя файла может быть дополнено с указанием пути.</span><span class="sxs-lookup"><span data-stu-id="cbff2-107">The file name can be qualified with a path.</span></span> <span data-ttu-id="cbff2-108">Заключите `filename` в двойные кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="cbff2-108">Enclose `filename` in double quotation marks (" ").</span></span>  
  
 `tagpath`  
 <span data-ttu-id="cbff2-109">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="cbff2-109">Required.</span></span> <span data-ttu-id="cbff2-110">Путь тегов в `filename`, который ведет к тегу `name`.</span><span class="sxs-lookup"><span data-stu-id="cbff2-110">The path of the tags in `filename` that leads to the tag `name`.</span></span> <span data-ttu-id="cbff2-111">Заключите путь в двойные кавычки ("").</span><span class="sxs-lookup"><span data-stu-id="cbff2-111">Enclose the path in double quotation marks (" ").</span></span>  
  
 `name`  
 <span data-ttu-id="cbff2-112">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="cbff2-112">Required.</span></span> <span data-ttu-id="cbff2-113">Описатель имени в теге, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="cbff2-113">The name specifier in the tag that precedes the comments.</span></span> <span data-ttu-id="cbff2-114">`Name` будет иметь `id` .</span><span class="sxs-lookup"><span data-stu-id="cbff2-114">`Name` will have an `id`.</span></span>  
  
 `id`  
 <span data-ttu-id="cbff2-115">Обязательный элемент.</span><span class="sxs-lookup"><span data-stu-id="cbff2-115">Required.</span></span> <span data-ttu-id="cbff2-116">Идентификатор тега, который предшествует комментариям.</span><span class="sxs-lookup"><span data-stu-id="cbff2-116">The ID for the tag that precedes the comments.</span></span> <span data-ttu-id="cbff2-117">Заключите идентификатор в одинарные кавычки (' ').</span><span class="sxs-lookup"><span data-stu-id="cbff2-117">Enclose the ID in single quotation marks (' ').</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cbff2-118">Remarks</span><span class="sxs-lookup"><span data-stu-id="cbff2-118">Remarks</span></span>  

 <span data-ttu-id="cbff2-119">Используйте `<include>` тег для ссылки на комментарии в другом файле, описывающем типы и члены в исходном коде.</span><span class="sxs-lookup"><span data-stu-id="cbff2-119">Use the `<include>` tag to refer to comments in another file that describe the types and members in your source code.</span></span> <span data-ttu-id="cbff2-120">Этот способ является альтернативой размещению комментариев документации непосредственно в файле исходного кода.</span><span class="sxs-lookup"><span data-stu-id="cbff2-120">This is an alternative to placing documentation comments directly in your source code file.</span></span>  
  
 <span data-ttu-id="cbff2-121">`<include>`Тег использует рекомендацию W3C по языку XML Path (XPath) версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="cbff2-121">The `<include>` tag uses the W3C XML Path Language (XPath) Version 1.0 Recommendation.</span></span> <span data-ttu-id="cbff2-122">Дополнительные сведения о способах настройки `<include>` использования см. в разделе <https://www.w3.org/TR/xpath> .</span><span class="sxs-lookup"><span data-stu-id="cbff2-122">For more information about ways to customize your `<include>` use, see <https://www.w3.org/TR/xpath>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbff2-123">Пример</span><span class="sxs-lookup"><span data-stu-id="cbff2-123">Example</span></span>  

 <span data-ttu-id="cbff2-124">В этом примере `<include>` тег используется для импорта комментариев документации элемента из файла с именем `commentFile.xml` .</span><span class="sxs-lookup"><span data-stu-id="cbff2-124">This example uses the `<include>` tag to import member documentation comments from a file called `commentFile.xml`.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#4)]  
  
 <span data-ttu-id="cbff2-125">Формат `commentFile.xml` имеет следующий вид.</span><span class="sxs-lookup"><span data-stu-id="cbff2-125">The format of the `commentFile.xml` is as follows.</span></span>  
  
```xml  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbff2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cbff2-126">See also</span></span>

- [<span data-ttu-id="cbff2-127">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="cbff2-127">XML Comment Tags</span></span>](index.md)
