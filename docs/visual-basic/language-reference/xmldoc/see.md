---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 51eaaef2ddb88afbb52ab58b85ed1a58ba251c1e
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866448"
---
# <a name="see-visual-basic"></a><span data-ttu-id="72cc3-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="72cc3-101">\<see> (Visual Basic)</span></span>

<span data-ttu-id="72cc3-102">Указывает ссылку на другой элемент.</span><span class="sxs-lookup"><span data-stu-id="72cc3-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72cc3-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="72cc3-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="72cc3-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="72cc3-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="72cc3-105">Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="72cc3-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="72cc3-106">Компилятор проверяет, существует ли элемент кода, и передает `member` в имя элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="72cc3-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="72cc3-107">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="72cc3-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72cc3-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="72cc3-108">Remarks</span></span>  

 <span data-ttu-id="72cc3-109">Используйте `<see>` тег, чтобы указать ссылку в тексте.</span><span class="sxs-lookup"><span data-stu-id="72cc3-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="72cc3-110">Используется [\<seealso>](seealso.md) для обозначения текста, который может потребоваться отобразить в разделе "см. также".</span><span class="sxs-lookup"><span data-stu-id="72cc3-110">Use [\<seealso>](seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="72cc3-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="72cc3-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72cc3-112">Пример</span><span class="sxs-lookup"><span data-stu-id="72cc3-112">Example</span></span>  

 <span data-ttu-id="72cc3-113">В этом примере используется `<see>` тег в `UpdateRecord` разделе "Примечания" для ссылки на `DoesRecordExist` метод.</span><span class="sxs-lookup"><span data-stu-id="72cc3-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="72cc3-114">См. также</span><span class="sxs-lookup"><span data-stu-id="72cc3-114">See also</span></span>

- [<span data-ttu-id="72cc3-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="72cc3-115">XML Comment Tags</span></span>](index.md)
