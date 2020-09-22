---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: e3f386d2a1e15ea3e1519d6e1e5e31c34c73fb99
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872894"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="88449-101">\<exception> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88449-101">\<exception> (Visual Basic)</span></span>

<span data-ttu-id="88449-102">Указывает, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="88449-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88449-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="88449-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="88449-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="88449-104">Parameters</span></span>  

 `member`  
 <span data-ttu-id="88449-105">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="88449-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="88449-106">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="88449-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="88449-107">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="88449-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="88449-108">Описание.</span><span class="sxs-lookup"><span data-stu-id="88449-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88449-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="88449-109">Remarks</span></span>  

 <span data-ttu-id="88449-110">Используйте `<exception>` тег, чтобы указать, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="88449-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="88449-111">Этот тег применяется к определению метода.</span><span class="sxs-lookup"><span data-stu-id="88449-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="88449-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="88449-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88449-113">Пример</span><span class="sxs-lookup"><span data-stu-id="88449-113">Example</span></span>  

 <span data-ttu-id="88449-114">В этом примере `<exception>` тег используется для описания исключения, которое `IntDivide` может выдаваться функцией.</span><span class="sxs-lookup"><span data-stu-id="88449-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="88449-115">См. также</span><span class="sxs-lookup"><span data-stu-id="88449-115">See also</span></span>

- [<span data-ttu-id="88449-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="88449-116">XML Comment Tags</span></span>](index.md)
