---
title: "Использование манипуляций и инерции в приложении XNA"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: 7
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7d623a8c2276811ae443a4d745faffeeb79ffc6f
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a><span data-ttu-id="3cc76-102">Использование манипуляций и инерции в приложении XNA</span><span class="sxs-lookup"><span data-stu-id="3cc76-102">Using Manipulations and Inertia in an XNA Application</span></span>
<span data-ttu-id="3cc76-103">В этой статье описывается, как можно использовать  обработку манипуляций и инерции в приложении Microsoft XNA для управления движением элементов игры.</span><span class="sxs-lookup"><span data-stu-id="3cc76-103">This article describes how you can use manipulations and inertia processing in a Microsoft XNA application to control the movement of game pieces.</span></span> <span data-ttu-id="3cc76-104">Прежде чем приступить к чтению этой статьи, следует ознакомиться со статьей [Общие сведения о манипуляциях и инерции](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md). Кроме того, потребуется знакомство с основными концепциями программирования XNA.</span><span class="sxs-lookup"><span data-stu-id="3cc76-104">Before you read this article, you should be familiar with the [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) topic, and be familiar with basic XNA programming concepts.</span></span>  
  
 <span data-ttu-id="3cc76-105">Для выполнения задач, описанных в этой статье, проект XNA должен ссылаться на сборку <xref:System.Windows.Input.Manipulations>, а чтобы проект мог ссылаться на сборки XNA, на вашем компьютере должен быть установлен пакет [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([скачать](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)).</span><span class="sxs-lookup"><span data-stu-id="3cc76-105">To perform the tasks described in this article, your XNA project must reference the <xref:System.Windows.Input.Manipulations> assembly, and you must have [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([download](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) installed on your computer so that your project can reference the XNA assemblies.</span></span>  
  
## <a name="overview-of-functionality"></a><span data-ttu-id="3cc76-106">Обзор функциональных возможностей</span><span class="sxs-lookup"><span data-stu-id="3cc76-106">Overview of Functionality</span></span>  
 <span data-ttu-id="3cc76-107">В этой статье показано, как создать пользовательский класс, представляющий элемент игры, который использует обработку манипуляций и инерции.</span><span class="sxs-lookup"><span data-stu-id="3cc76-107">This article shows you how to create a custom class that represents a game piece that uses manipulation and inertia processing.</span></span> <span data-ttu-id="3cc76-108">Этот класс позволяет управлять элементом игры на экране, перетаскивая его с помощью мыши, а затем освобождая его.</span><span class="sxs-lookup"><span data-stu-id="3cc76-108">This class enables you to manipulate a game piece across the screen by dragging it with the mouse, and then releasing it.</span></span> <span data-ttu-id="3cc76-109">После освобождения обработка инерции сохраняет движение элемента, как будто он постепенно замедляется.</span><span class="sxs-lookup"><span data-stu-id="3cc76-109">Once released, inertia processing keeps the game piece moving as it gradually slows down.</span></span> <span data-ttu-id="3cc76-110">Перемещение как линейное, так и угловое.</span><span class="sxs-lookup"><span data-stu-id="3cc76-110">Movement is both linear and angular.</span></span>  
  
 <span data-ttu-id="3cc76-111">![Приложение простых манипуляций и инерции.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span><span class="sxs-lookup"><span data-stu-id="3cc76-111">![A simple manipulations and inertia application.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span></span>  
  
 <span data-ttu-id="3cc76-112">Кроме того, создается пользовательская коллекция, управляющая несколькими элементами игры.</span><span class="sxs-lookup"><span data-stu-id="3cc76-112">In addition, a custom collection is created that manages multiple game pieces.</span></span> <span data-ttu-id="3cc76-113">Это упрощает обработку, требуемую классом Game XNA. </span><span class="sxs-lookup"><span data-stu-id="3cc76-113">This simplifies the handling that is required from the XNA Game class.</span></span>  
  
 [<span data-ttu-id="3cc76-114">Создание класса GamePiece</span><span class="sxs-lookup"><span data-stu-id="3cc76-114">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [<span data-ttu-id="3cc76-115">Создание класса GamePieceCollection</span><span class="sxs-lookup"><span data-stu-id="3cc76-115">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [<span data-ttu-id="3cc76-116">Создание класса Game1</span><span class="sxs-lookup"><span data-stu-id="3cc76-116">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [<span data-ttu-id="3cc76-117">Полные листинги кода</span><span class="sxs-lookup"><span data-stu-id="3cc76-117">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a><span data-ttu-id="3cc76-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3cc76-118">See Also</span></span>  
 <span data-ttu-id="3cc76-119"><xref:System.Windows.Input.Manipulations></span><span class="sxs-lookup"><span data-stu-id="3cc76-119"><xref:System.Windows.Input.Manipulations></span></span>   
 [<span data-ttu-id="3cc76-120">Общие сведения о манипуляциях и инерции</span><span class="sxs-lookup"><span data-stu-id="3cc76-120">Manipulations and Inertia Overview</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
