---
title: Практическое руководство. Создание метода добавления расширения, используемого инициализатором коллекции
ms.date: 07/20/2015
helpviewer_keywords:
- collection initializers [Visual Basic]
ms.assetid: f64b52c7-8b11-4410-93a6-cb3aeebcc772
ms.openlocfilehash: c36fab6635a9f7820c52c5f73c20487b92879b9a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086352"
---
# <a name="how-to-create-an-add-extension-method-used-by-a-collection-initializer-visual-basic"></a><span data-ttu-id="6a58d-102">Практическое руководство. Создание метода расширения Add, используемого инициализатором набора (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a58d-102">How to: Create an Add Extension Method Used by a Collection Initializer (Visual Basic)</span></span>

<span data-ttu-id="6a58d-103">При использовании инициализатора коллекции для создания коллекции компилятор Visual Basic выполняет поиск `Add` метода типа коллекции, для которого параметры `Add` метода соответствуют типам значений в инициализаторе коллекции.</span><span class="sxs-lookup"><span data-stu-id="6a58d-103">When you use a collection initializer to create a collection, the Visual Basic compiler searches for an `Add` method of the collection type for which the parameters for the `Add` method match the types of the values in the collection initializer.</span></span> <span data-ttu-id="6a58d-104">Этот `Add` метод используется для заполнения коллекции значениями из инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="6a58d-104">This `Add` method is used to populate the collection with the values from the collection initializer.</span></span>  
  
 <span data-ttu-id="6a58d-105">Если соответствующий `Add` метод не существует и вы не можете изменить код для коллекции, можно добавить метод расширения `Add` с именем, принимающий параметры, необходимые инициализатору коллекции.</span><span class="sxs-lookup"><span data-stu-id="6a58d-105">If no matching `Add` method exists and you cannot modify the code for the collection, you can add an extension method called `Add` that takes the parameters that are required by the collection initializer.</span></span> <span data-ttu-id="6a58d-106">Обычно это необходимо сделать при использовании инициализаторов коллекций для универсальных коллекций.</span><span class="sxs-lookup"><span data-stu-id="6a58d-106">This is typically what you need to do when you use collection initializers for generic collections.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a58d-107">Пример</span><span class="sxs-lookup"><span data-stu-id="6a58d-107">Example</span></span>  

 <span data-ttu-id="6a58d-108">В следующем примере показано, как добавить метод расширения в универсальный тип, <xref:System.Collections.Generic.List%601> чтобы инициализатор коллекции можно было использовать для добавления объектов типа `Employee` .</span><span class="sxs-lookup"><span data-stu-id="6a58d-108">The following example shows how to add an extension method to the generic <xref:System.Collections.Generic.List%601> type so that a collection initializer can be used to add objects of type `Employee`.</span></span> <span data-ttu-id="6a58d-109">Метод расширения позволяет использовать сокращенный синтаксис инициализатора коллекции.</span><span class="sxs-lookup"><span data-stu-id="6a58d-109">The extension method enables you to use the shortened collection initializer syntax.</span></span>  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#1)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#2)]  
  
 [!code-vb[VbVbalrCollectionInitializersHowTo1#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCollectionInitializersHowTo1/VB/Module1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6a58d-110">См. также</span><span class="sxs-lookup"><span data-stu-id="6a58d-110">See also</span></span>

- [<span data-ttu-id="6a58d-111">Инициализаторы коллекций</span><span class="sxs-lookup"><span data-stu-id="6a58d-111">Collection Initializers</span></span>](index.md)
- [<span data-ttu-id="6a58d-112">Практическое руководство. Создание коллекции с помощью инициализатора набора</span><span class="sxs-lookup"><span data-stu-id="6a58d-112">How to: Create a Collection Used by a Collection Initializer</span></span>](how-to-create-a-collection-used-by-a-collection-initializer.md)
