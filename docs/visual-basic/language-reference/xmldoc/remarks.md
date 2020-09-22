---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 70078752495240ab8c72fe1bbecdca554166fb22
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866419"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="22158-101">\<remarks> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="22158-101">\<remarks> (Visual Basic)</span></span>

<span data-ttu-id="22158-102">Задает раздел примечаний для элемента.</span><span class="sxs-lookup"><span data-stu-id="22158-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22158-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="22158-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="22158-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="22158-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="22158-105">Описание элемента.</span><span class="sxs-lookup"><span data-stu-id="22158-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22158-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="22158-106">Remarks</span></span>  

 <span data-ttu-id="22158-107">Используйте `<remarks>` тег, чтобы добавить сведения о типе, добавив сведения, указанные в параметре [\<summary>](summary.md) .</span><span class="sxs-lookup"><span data-stu-id="22158-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](summary.md).</span></span>  
  
 <span data-ttu-id="22158-108">Эти сведения отображаются в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="22158-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="22158-109">Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="22158-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="22158-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="22158-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22158-111">Пример</span><span class="sxs-lookup"><span data-stu-id="22158-111">Example</span></span>  

 <span data-ttu-id="22158-112">В этом примере `<remarks>` тег используется для объяснения того, что `UpdateRecord` делает метод.</span><span class="sxs-lookup"><span data-stu-id="22158-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="22158-113">См. также</span><span class="sxs-lookup"><span data-stu-id="22158-113">See also</span></span>

- [<span data-ttu-id="22158-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="22158-114">XML Comment Tags</span></span>](index.md)
