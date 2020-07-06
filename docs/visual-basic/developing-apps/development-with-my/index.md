---
title: Разработка с использованием My
ms.date: 07/20/2015
f1_keywords:
- My.MyWpfExtension.Windows
helpviewer_keywords:
- My object
- My namespace
- My feature
- Visual Basic, programming in
ms.assetid: f1d04509-5e46-4551-9f9f-94334a121fca
ms.openlocfilehash: 3befac591de8fbc7250777a8b87247ee395abf25
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2020
ms.locfileid: "85840354"
---
# <a name="development-with-my-visual-basic"></a><span data-ttu-id="4a74a-102">Разработка с использованием My (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a74a-102">Development with My (Visual Basic)</span></span>

<span data-ttu-id="4a74a-103">Visual Basic предоставляет новые функции для быстрой разработки приложений, которые повышают производительность, упрощают работу и предоставляют богатые возможности.</span><span class="sxs-lookup"><span data-stu-id="4a74a-103">Visual Basic provides new features for rapid application development that improve productivity and ease of use while delivering power.</span></span> <span data-ttu-id="4a74a-104">Одна из этих функций, называемая `My`, предоставляет доступ к информации и экземплярам объектов по умолчанию, относящихся к приложению и среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="4a74a-104">One of these features, called `My`, provides access to information and default object instances that are related to the application and its run-time environment.</span></span> <span data-ttu-id="4a74a-105">Эта информация организована в формате, который обнаруживается через IntelliSense и логически разделен в соответствии с использованием.</span><span class="sxs-lookup"><span data-stu-id="4a74a-105">This information is organized in a format that is discoverable through IntelliSense and logically delineated according to use.</span></span>  
  
 <span data-ttu-id="4a74a-106">Члены верхнего уровня `My` представляются как объекты.</span><span class="sxs-lookup"><span data-stu-id="4a74a-106">Top-level members of `My` are exposed as objects.</span></span> <span data-ttu-id="4a74a-107">Каждый объект ведет себя как пространство имен или класса с членами `Shared`, предоставляя набор связанных элементов.</span><span class="sxs-lookup"><span data-stu-id="4a74a-107">Each object behaves similarly to a namespace or a class with `Shared` members, and it exposes a set of related members.</span></span>  
  
 <span data-ttu-id="4a74a-108">В следующей таблице перечислены объекты `My` верхнего уровня и их связь друг с другом.</span><span class="sxs-lookup"><span data-stu-id="4a74a-108">This table shows the top-level `My` objects and their relationship to each other.</span></span>  
  
 ![На этом рисунке показана модель объектов для My.](./media/index/my-object-model-relationships.gif)  
  
## <a name="in-this-section"></a><span data-ttu-id="4a74a-110">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="4a74a-110">In This Section</span></span>  

 [<span data-ttu-id="4a74a-111">Выполнение задач с помощью My.Application, My.Computer и My.User</span><span class="sxs-lookup"><span data-stu-id="4a74a-111">Performing Tasks with My.Application, My.Computer, and My.User</span></span>](performing-tasks-with-my-application-my-computer-and-my-user.md)  
 <span data-ttu-id="4a74a-112">Описывает трех центральных объекта `My`, (`My.Application`, `My.Computer` и `My.User`), которые обеспечивают доступ к информации и функциональным возможностям</span><span class="sxs-lookup"><span data-stu-id="4a74a-112">Describes the three central `My` objects, `My.Application`, `My.Computer`, and `My.User`, which provide access to information and functionality</span></span>  
  
 [<span data-ttu-id="4a74a-113">Экземпляры объектов, которые My.Forms и My.WebServices предоставляют по умолчанию</span><span class="sxs-lookup"><span data-stu-id="4a74a-113">Default Object Instances Provided by My.Forms and My.WebServices</span></span>](default-object-instances-provided-by-my-forms-and-my-webservices.md)  
 <span data-ttu-id="4a74a-114">Описывает объекты `My.Forms` и `My.WebServices`, которые предоставляют доступ к формам, источникам данных и веб-службам XML, используемым приложениями.</span><span class="sxs-lookup"><span data-stu-id="4a74a-114">Describes the `My.Forms` and `My.WebServices` objects, which provide access to forms, data sources, and XML Web services used by your application.</span></span>  
  
 [<span data-ttu-id="4a74a-115">Быстрая разработка приложений с использованием My.Resources и My.Settings</span><span class="sxs-lookup"><span data-stu-id="4a74a-115">Rapid Application Development with My.Resources and My.Settings</span></span>](rapid-application-development-with-my-resources-and-my-settings.md)  
 <span data-ttu-id="4a74a-116">Описывает объекты `My.Resources` и `My.Settings`, которые предоставляют доступ к ресурсам и параметрам приложения.</span><span class="sxs-lookup"><span data-stu-id="4a74a-116">Describes the `My.Resources` and `My.Settings` objects, which provide access to an application's resources and settings.</span></span>  
  
 [<span data-ttu-id="4a74a-117">Обзор модели приложения в Visual Basic</span><span class="sxs-lookup"><span data-stu-id="4a74a-117">Overview of the Visual Basic Application Model</span></span>](overview-of-the-visual-basic-application-model.md)  
 <span data-ttu-id="4a74a-118">Описывает модель запуска и завершения работы приложения в Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4a74a-118">Describes the Visual Basic Application Startup/Shutdown model.</span></span>  
  
 [<span data-ttu-id="4a74a-119">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="4a74a-119">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)  
 <span data-ttu-id="4a74a-120">Предоставляет подробные сведения о том, какие функции `My` доступны в разных типах проектов.</span><span class="sxs-lookup"><span data-stu-id="4a74a-120">Gives details on which `My` features are available in different project types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a74a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="4a74a-121">See also</span></span>

- <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>
- <xref:Microsoft.VisualBasic.Devices.Computer>
- <xref:Microsoft.VisualBasic.ApplicationServices.User>
- [<span data-ttu-id="4a74a-122">Объект My.Forms</span><span class="sxs-lookup"><span data-stu-id="4a74a-122">My.Forms Object</span></span>](../../language-reference/objects/my-forms-object.md)
- [<span data-ttu-id="4a74a-123">Объект My.WebServices</span><span class="sxs-lookup"><span data-stu-id="4a74a-123">My.WebServices Object</span></span>](../../language-reference/objects/my-webservices-object.md)
- [<span data-ttu-id="4a74a-124">Зависимость My от типа проекта</span><span class="sxs-lookup"><span data-stu-id="4a74a-124">How My Depends on Project Type</span></span>](how-my-depends-on-project-type.md)
