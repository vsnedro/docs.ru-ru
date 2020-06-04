---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 2ad54845645172acb5b91935f5347a828510e3aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411490"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="5c2ee-101">\<typeparam> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5c2ee-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="5c2ee-102">Определяет имя и описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="5c2ee-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c2ee-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c2ee-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c2ee-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c2ee-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="5c2ee-105">Имя параметра типа.</span><span class="sxs-lookup"><span data-stu-id="5c2ee-105">The name of the type parameter.</span></span> <span data-ttu-id="5c2ee-106">Имя заключается в двойные кавычки (" ").</span><span class="sxs-lookup"><span data-stu-id="5c2ee-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="5c2ee-107">Описание параметра типа.</span><span class="sxs-lookup"><span data-stu-id="5c2ee-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c2ee-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="5c2ee-108">Remarks</span></span>  
 <span data-ttu-id="5c2ee-109">Используйте `<typeparam>` тег в комментарии для объявления универсального типа или универсального члена, чтобы описать один из параметров типа.</span><span class="sxs-lookup"><span data-stu-id="5c2ee-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="5c2ee-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="5c2ee-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c2ee-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5c2ee-111">Example</span></span>  
 <span data-ttu-id="5c2ee-112">В этом примере `<typeparam>` для описания параметра используется тег `id` .</span><span class="sxs-lookup"><span data-stu-id="5c2ee-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="5c2ee-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5c2ee-113">See also</span></span>

- [<span data-ttu-id="5c2ee-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="5c2ee-114">XML Comment Tags</span></span>](index.md)
