---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 893ed299b46bd6255ca0e87d008ac53265698614
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411503"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="bcd4d-101">\<summary> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bcd4d-101">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="bcd4d-102">Указывает сводку элемента.</span><span class="sxs-lookup"><span data-stu-id="bcd4d-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcd4d-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bcd4d-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="bcd4d-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="bcd4d-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="bcd4d-105">Сводка объекта.</span><span class="sxs-lookup"><span data-stu-id="bcd4d-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bcd4d-106">Remarks</span><span class="sxs-lookup"><span data-stu-id="bcd4d-106">Remarks</span></span>  
 <span data-ttu-id="bcd4d-107">Используйте `<summary>` тег для описания типа или члена типа.</span><span class="sxs-lookup"><span data-stu-id="bcd4d-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="bcd4d-108">Используйте [\<remarks>](remarks.md) для добавления дополнительных сведений в описание типа.</span><span class="sxs-lookup"><span data-stu-id="bcd4d-108">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="bcd4d-109">Текст для `<summary>` тега — единственный источник сведений о типе в IntelliSense, который также отображается в обозревателе объектов.</span><span class="sxs-lookup"><span data-stu-id="bcd4d-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="bcd4d-110">Дополнительные сведения об обозревателе объектов см. [в разделе Просмотр структуры кода](/visualstudio/ide/viewing-the-structure-of-code).</span><span class="sxs-lookup"><span data-stu-id="bcd4d-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="bcd4d-111">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="bcd4d-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bcd4d-112">Пример</span><span class="sxs-lookup"><span data-stu-id="bcd4d-112">Example</span></span>  
 <span data-ttu-id="bcd4d-113">В этом примере используется `<summary>` тег для описания `ResetCounter` метода и `Counter` Свойства.</span><span class="sxs-lookup"><span data-stu-id="bcd4d-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="bcd4d-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bcd4d-114">See also</span></span>

- [<span data-ttu-id="bcd4d-115">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="bcd4d-115">XML Comment Tags</span></span>](index.md)
