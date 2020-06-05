---
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: aa65fed863718f1f00b510f82051a13e764e1b23
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400152"
---
# <a name="code-visual-basic"></a><span data-ttu-id="c3b0c-101">\<code> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c3b0c-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="c3b0c-102">Указывает, что текст представляет собой несколько строк кода.</span><span class="sxs-lookup"><span data-stu-id="c3b0c-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3b0c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3b0c-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3b0c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3b0c-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="c3b0c-105">Текст, помечающий как код.</span><span class="sxs-lookup"><span data-stu-id="c3b0c-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3b0c-106">Комментарии</span><span class="sxs-lookup"><span data-stu-id="c3b0c-106">Remarks</span></span>  
 <span data-ttu-id="c3b0c-107">Используйте `<code>` тег, чтобы указать несколько строк в виде кода.</span><span class="sxs-lookup"><span data-stu-id="c3b0c-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="c3b0c-108">Используйте, [\<c>](c.md) чтобы указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="c3b0c-108">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="c3b0c-109">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="c3b0c-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3b0c-110">Пример</span><span class="sxs-lookup"><span data-stu-id="c3b0c-110">Example</span></span>  
 <span data-ttu-id="c3b0c-111">В этом примере \<code> тег используется для включения примера кода для использования `ID` поля.</span><span class="sxs-lookup"><span data-stu-id="c3b0c-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c3b0c-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c3b0c-112">See also</span></span>

- [<span data-ttu-id="c3b0c-113">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="c3b0c-113">XML Comment Tags</span></span>](index.md)
