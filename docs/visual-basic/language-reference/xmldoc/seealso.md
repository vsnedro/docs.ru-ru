---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: f435fa2ab86d81053cd185f5d90ec22996a1458d
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90869410"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="56c16-101">\<seealso> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56c16-101">\<seealso> (Visual Basic)</span></span>

<span data-ttu-id="56c16-102">Указывает ссылку, которая отображается в разделе "см. также".</span><span class="sxs-lookup"><span data-stu-id="56c16-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56c16-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="56c16-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="56c16-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="56c16-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="56c16-105">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="56c16-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="56c16-106">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="56c16-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="56c16-107">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="56c16-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56c16-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="56c16-108">Remarks</span></span>  

 <span data-ttu-id="56c16-109">Используйте `<seealso>` тег, чтобы указать текст, который должен отображаться в разделе "см. также".</span><span class="sxs-lookup"><span data-stu-id="56c16-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="56c16-110">Тег [\<see>](see.md) позволяет задать ссылку из текста.</span><span class="sxs-lookup"><span data-stu-id="56c16-110">Use [\<see>](see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="56c16-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="56c16-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56c16-112">Пример</span><span class="sxs-lookup"><span data-stu-id="56c16-112">Example</span></span>  

 <span data-ttu-id="56c16-113">В этом примере используется `<seealso>` тег в `DoesRecordExist` разделе "Примечания" для ссылки на `UpdateRecord` метод.</span><span class="sxs-lookup"><span data-stu-id="56c16-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="56c16-114">См. также</span><span class="sxs-lookup"><span data-stu-id="56c16-114">See also</span></span>

- [<span data-ttu-id="56c16-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="56c16-115">XML Comment Tags</span></span>](index.md)
