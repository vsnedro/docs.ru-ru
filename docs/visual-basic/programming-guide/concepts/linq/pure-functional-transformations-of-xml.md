---
title: Чистые функциональные преобразования XML
ms.date: 07/20/2015
ms.assetid: 5e19b74a-7773-4b58-b110-953ffd364c55
ms.openlocfilehash: 60ec6a5f9c643ea5cc0511f48356d6bfa3ad5748
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396328"
---
# <a name="pure-functional-transformations-of-xml-visual-basic"></a><span data-ttu-id="0b8ff-102">Чистые функциональные преобразования XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b8ff-102">Pure Functional Transformations of XML (Visual Basic)</span></span>
<span data-ttu-id="0b8ff-103">В этом разделе приведен учебник по функциональным преобразованиям для XML.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-103">This section provides a functional transformation tutorial for XML.</span></span> <span data-ttu-id="0b8ff-104">В учебнике разъясняются основные принципы и языковые конструкции, которые необходимо понять, чтобы использовать функциональные преобразования. В нем также рассказывается об использовании функциональных преобразований для обработки XML-документа.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-104">This includes explanations of the main concepts and language constructs that you must understand to use functional transformations, and examples of using functional transformations to manipulate an XML document.</span></span> <span data-ttu-id="0b8ff-105">Несмотря на то что в этом учебнике приведены примеры кода LINQ to XML, все базовые принципы также применяются и к другим технологиям LINQ.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-105">Although this tutorial provides LINQ to XML code examples, all of the underlying concepts also apply to other LINQ technologies.</span></span>  
  
 <span data-ttu-id="0b8ff-106">Руководство по [управлению содержимым в документе WordprocessingML (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) содержит ряд примеров, каждый из которых строится на предыдущем.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-106">The [Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)](tutorial-manipulating-content-in-a-wordprocessingml-document.md) tutorial provides a series of examples, each building on the previous one.</span></span> <span data-ttu-id="0b8ff-107">Эти примеры демонстрируют подход с использованием чисто функциональных преобразований для обработки XML.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-107">These examples demonstrate the pure functional transformational approach to manipulating XML.</span></span>  
  
 <span data-ttu-id="0b8ff-108">В этом учебнике предполагается, что у вас есть опыт работы с Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-108">This tutorial assumes a working knowledge of Visual Basic.</span></span> <span data-ttu-id="0b8ff-109">В этом учебнике не приводится подробное описание семантики и языковых конструкций, однако в нем есть ссылки на соответствующую документацию по языку.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-109">Detailed semantics of the language constructs are not provided in this tutorial, but links are provided to the language documentation as appropriate.</span></span>  
  
 <span data-ttu-id="0b8ff-110">Требуются также твердые знания базовых принципов программирования и XML, в том числе пространств имен XML.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-110">A working knowledge of basic computer science concepts and XML, including XML namespaces, is also assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0b8ff-111">в этом разделе</span><span class="sxs-lookup"><span data-stu-id="0b8ff-111">In This Section</span></span>  
  
|<span data-ttu-id="0b8ff-112">Раздел</span><span class="sxs-lookup"><span data-stu-id="0b8ff-112">Topic</span></span>|<span data-ttu-id="0b8ff-113">Описание</span><span class="sxs-lookup"><span data-stu-id="0b8ff-113">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0b8ff-114">Введение в чистые функциональные преобразования (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b8ff-114">Introduction to Pure Functional Transformations (Visual Basic)</span></span>](introduction-to-pure-functional-transformations.md)|<span data-ttu-id="0b8ff-115">Описывает функциональные преобразования и определяет соответствующую технологию.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-115">Describes functional transformations and defines the relevant terminology.</span></span>|  
|[<span data-ttu-id="0b8ff-116">Учебник. отложенное выполнение (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b8ff-116">Tutorial: Deferred Execution (Visual Basic)</span></span>](tutorial-deferred-execution.md)|<span data-ttu-id="0b8ff-117">Подробно описывает отложенное вычисление и отложенное выполнение.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-117">Describes lazy evaluation and deferred execution in detail.</span></span>|  
|[<span data-ttu-id="0b8ff-118">Руководство. Управление содержимым в документе WordprocessingML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b8ff-118">Tutorial: Manipulating Content in a WordprocessingML Document (Visual Basic)</span></span>](tutorial-manipulating-content-in-a-wordprocessingml-document.md)|<span data-ttu-id="0b8ff-119">Учебник, в котором демонстрируется функциональное преобразование.</span><span class="sxs-lookup"><span data-stu-id="0b8ff-119">A tutorial that demonstrates a functional transformation.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0b8ff-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0b8ff-120">See also</span></span>

- [<span data-ttu-id="0b8ff-121">Выполнение запросов к деревьям XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0b8ff-121">Querying XML Trees (Visual Basic)</span></span>](querying-xml-trees.md)
