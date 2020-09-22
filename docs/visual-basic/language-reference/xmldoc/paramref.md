---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: d7aacc5faea22f9c5a4b865a32c832154fe624c5
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872610"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="bd890-101">\<paramref> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd890-101">\<paramref> (Visual Basic)</span></span>

<span data-ttu-id="bd890-102">Форматирует слово как параметр.</span><span class="sxs-lookup"><span data-stu-id="bd890-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd890-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd890-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd890-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd890-104">Parameters</span></span>  

 `name`  
 <span data-ttu-id="bd890-105">Имя параметра, на который указывается ссылка.</span><span class="sxs-lookup"><span data-stu-id="bd890-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="bd890-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="bd890-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd890-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd890-107">Remarks</span></span>  

 <span data-ttu-id="bd890-108">`<paramref>`Тег дает возможность указать, что слово является параметром.</span><span class="sxs-lookup"><span data-stu-id="bd890-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="bd890-109">XML-файл может быть обработан для того, чтобы отформатировать этот параметр определенным образом.</span><span class="sxs-lookup"><span data-stu-id="bd890-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="bd890-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="bd890-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bd890-111">Пример</span><span class="sxs-lookup"><span data-stu-id="bd890-111">Example</span></span>  

 <span data-ttu-id="bd890-112">В этом примере `<paramref>` тег используется для ссылки на `id` параметр.</span><span class="sxs-lookup"><span data-stu-id="bd890-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="bd890-113">См. также</span><span class="sxs-lookup"><span data-stu-id="bd890-113">See also</span></span>

- [<span data-ttu-id="bd890-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="bd890-114">XML Comment Tags</span></span>](index.md)
