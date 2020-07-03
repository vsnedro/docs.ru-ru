---
title: Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 141f2f5f98499498d3c6732f7ae8d0abe6259ed9
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990240"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a><span data-ttu-id="c642c-102">Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c642c-102">Default Object Instances Provided by My.Forms and My.WebServices (Visual Basic)</span></span>

<span data-ttu-id="c642c-103">Объекты [My.Forms](../../language-reference/objects/my-forms-object.md) и [My.WebServices](../../language-reference/objects/my-webservices-object.md) предоставляют доступ к формам, источникам данных и веб-службам XML, используемым вашим приложением.</span><span class="sxs-lookup"><span data-stu-id="c642c-103">The [My.Forms](../../language-reference/objects/my-forms-object.md) and [My.WebServices](../../language-reference/objects/my-webservices-object.md) objects provide access to forms, data sources, and XML Web services used by your application.</span></span> <span data-ttu-id="c642c-104">Для этого они используют коллекции *экземпляров по умолчанию* каждого из этих объектов.</span><span class="sxs-lookup"><span data-stu-id="c642c-104">They provide access through collections of *default instances* of each of these objects.</span></span>  
  
## <a name="default-instances"></a><span data-ttu-id="c642c-105">Экземпляры по умолчанию</span><span class="sxs-lookup"><span data-stu-id="c642c-105">Default Instances</span></span>  

 <span data-ttu-id="c642c-106">Экземпляр по умолчанию — это экземпляр класса, который предоставляется средой выполнения и не требует объявления и создания экземпляра с помощью инструкций `Dim` и `New`.</span><span class="sxs-lookup"><span data-stu-id="c642c-106">A default instance is an instance of the class that is provided by the runtime and does not need to be declared and instantiated using the `Dim` and `New` statements.</span></span> <span data-ttu-id="c642c-107">В следующем примере показано, как раньше можно было объявить и создать экземпляр класса <xref:System.Windows.Forms.Form> с именем `Form1` и как теперь можно получить экземпляр по умолчанию этого класса <xref:System.Windows.Forms.Form> через `My.Forms`.</span><span class="sxs-lookup"><span data-stu-id="c642c-107">The following example demonstrates how you might have declared and instantiated an instance of a <xref:System.Windows.Forms.Form> class called `Form1`, and how you are now able to get a default instance of this <xref:System.Windows.Forms.Form> class through `My.Forms`.</span></span>  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 <span data-ttu-id="c642c-108">Объект `My.Forms` возвращает коллекцию экземпляров по умолчанию для каждого класса `Form`, существующего в проекте.</span><span class="sxs-lookup"><span data-stu-id="c642c-108">The `My.Forms` object returns a collection of default instances for every `Form` class that exists in your project.</span></span> <span data-ttu-id="c642c-109">Аналогичным образом, `My.WebServices` предоставляет экземпляр прокси-класса по умолчанию для каждой веб-службы, на которую вы ссылались в приложении.</span><span class="sxs-lookup"><span data-stu-id="c642c-109">Similarly, `My.WebServices` provides a default instance of the proxy class for every Web service that you have created a reference to in your application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c642c-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c642c-110">See also</span></span>

- [<span data-ttu-id="c642c-111">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="c642c-111">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="c642c-112">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="c642c-112">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="c642c-113">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="c642c-113">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
