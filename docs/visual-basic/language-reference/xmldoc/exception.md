---
title: <exception>
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 3a2452ec60a2182adfee365777d9824001ff006a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400128"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="c827c-101">\<exception> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c827c-101">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="c827c-102">Указывает, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="c827c-102">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c827c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c827c-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c827c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="c827c-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="c827c-105">Ссылка на исключение, которое доступно из текущей среды компиляции.</span><span class="sxs-lookup"><span data-stu-id="c827c-105">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="c827c-106">Компилятор проверяет, существует ли исключение, и приводит `member` к каноническому имени элемента в выходных XML-данных.</span><span class="sxs-lookup"><span data-stu-id="c827c-106">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c827c-107">`member` необходимо заключать в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="c827c-107">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c827c-108">Описание.</span><span class="sxs-lookup"><span data-stu-id="c827c-108">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c827c-109">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c827c-109">Remarks</span></span>  
 <span data-ttu-id="c827c-110">Используйте `<exception>` тег, чтобы указать, какие исключения могут быть созданы.</span><span class="sxs-lookup"><span data-stu-id="c827c-110">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="c827c-111">Этот тег применяется к определению метода.</span><span class="sxs-lookup"><span data-stu-id="c827c-111">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="c827c-112">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="c827c-112">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c827c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="c827c-113">Example</span></span>  
 <span data-ttu-id="c827c-114">В этом примере `<exception>` тег используется для описания исключения, которое `IntDivide` может выдаваться функцией.</span><span class="sxs-lookup"><span data-stu-id="c827c-114">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c827c-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c827c-115">See also</span></span>

- [<span data-ttu-id="c827c-116">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="c827c-116">XML Comment Tags</span></span>](index.md)
