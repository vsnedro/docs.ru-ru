---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 550f8b63928f80878ba316bfaf09077e14091305
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875179"
---
# <a name="value-visual-basic"></a><span data-ttu-id="68c24-101">\<value> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68c24-101">\<value> (Visual Basic)</span></span>

<span data-ttu-id="68c24-102">Задает описание свойства.</span><span class="sxs-lookup"><span data-stu-id="68c24-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68c24-103">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="68c24-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="68c24-104">Параметры</span><span class="sxs-lookup"><span data-stu-id="68c24-104">Parameters</span></span>  

 `property-description`  
 <span data-ttu-id="68c24-105">Описание свойства.</span><span class="sxs-lookup"><span data-stu-id="68c24-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="68c24-106">Примечания</span><span class="sxs-lookup"><span data-stu-id="68c24-106">Remarks</span></span>  

 <span data-ttu-id="68c24-107">Используйте `<value>` тег для описания свойства.</span><span class="sxs-lookup"><span data-stu-id="68c24-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="68c24-108">Обратите внимание, что при добавлении свойства с помощью мастера кода в среде разработки Visual Studio будет добавлен [\<summary>](summary.md) тег для нового свойства.</span><span class="sxs-lookup"><span data-stu-id="68c24-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="68c24-109">После этого следует вручную добавить тег `<value>` для описания значения, которое представляется свойством.</span><span class="sxs-lookup"><span data-stu-id="68c24-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="68c24-110">Чтобы обработать комментарии документации и сохранить их в файл, выполняйте сборку с параметром [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="68c24-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68c24-111">Пример</span><span class="sxs-lookup"><span data-stu-id="68c24-111">Example</span></span>  

 <span data-ttu-id="68c24-112">В этом примере `<value>` тег используется для описания значения, которое `Counter` содержит свойство.</span><span class="sxs-lookup"><span data-stu-id="68c24-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="68c24-113">См. также</span><span class="sxs-lookup"><span data-stu-id="68c24-113">See also</span></span>

- [<span data-ttu-id="68c24-114">XML-теги для комментариев</span><span class="sxs-lookup"><span data-stu-id="68c24-114">XML Comment Tags</span></span>](index.md)
