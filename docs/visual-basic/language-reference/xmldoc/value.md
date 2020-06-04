---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411477"
---
# <a name="value-visual-basic"></a><span data-ttu-id="d7e8e-101">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d7e8e-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="d7e8e-102">Задает описание свойства.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7e8e-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7e8e-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7e8e-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7e8e-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="d7e8e-105">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7e8e-106">Комментарии</span><span class="sxs-lookup"><span data-stu-id="d7e8e-106">Remarks</span></span>  
 <span data-ttu-id="d7e8e-107">Используйте `<value>` тег для описания свойства.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="d7e8e-108">Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio будет добавлен [\<summary>](summary.md) тег для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="d7e8e-109">Затем следует вручную добавить `<value>` тег для описания значения, которое представляет свойство.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="d7e8e-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="d7e8e-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7e8e-111">Пример</span><span class="sxs-lookup"><span data-stu-id="d7e8e-111">Example</span></span>  
 <span data-ttu-id="d7e8e-112">В этом примере `<value>` тег используется для описания значения, которое `Counter` содержит свойство.</span><span class="sxs-lookup"><span data-stu-id="d7e8e-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="d7e8e-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="d7e8e-113">See also</span></span>

- [<span data-ttu-id="d7e8e-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="d7e8e-114">XML Comment Tags</span></span>](index.md)
