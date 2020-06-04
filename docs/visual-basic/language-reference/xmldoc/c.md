---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: c8ba03d9cc01c4751d15c01530c6cbf7d499dc3b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400167"
---
# <a name="c-visual-basic"></a><span data-ttu-id="9605c-101">\<c> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9605c-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="9605c-102">Указывает, что текст в описании является кодом.</span><span class="sxs-lookup"><span data-stu-id="9605c-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9605c-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9605c-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9605c-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="9605c-104">Parameters</span></span>  
  
|<span data-ttu-id="9605c-105">Параметр</span><span class="sxs-lookup"><span data-stu-id="9605c-105">Parameter</span></span>|<span data-ttu-id="9605c-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9605c-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="9605c-107">Текст, который нужно указать в качестве кода.</span><span class="sxs-lookup"><span data-stu-id="9605c-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9605c-108">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9605c-108">Remarks</span></span>  
 <span data-ttu-id="9605c-109">`<c>`Тег дает возможность указать, что текст в описании должен быть помечен как код.</span><span class="sxs-lookup"><span data-stu-id="9605c-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="9605c-110">Используется [\<code>](code.md) для указания нескольких строк в виде кода.</span><span class="sxs-lookup"><span data-stu-id="9605c-110">Use [\<code>](code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="9605c-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="9605c-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9605c-112">Пример</span><span class="sxs-lookup"><span data-stu-id="9605c-112">Example</span></span>  
 <span data-ttu-id="9605c-113">В этом примере `<c>` тег в разделе сводки используется для указания того, что `Counter` является кодом.</span><span class="sxs-lookup"><span data-stu-id="9605c-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="9605c-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9605c-114">See also</span></span>

- [<span data-ttu-id="9605c-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="9605c-115">XML Comment Tags</span></span>](index.md)
