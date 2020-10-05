---
title: Практическое руководство. Создание службы программным способом
description: Узнайте, как создать службу программным способом, самостоятельно настроив наследование и другие элементы инфраструктуры.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- services, creating
- Windows Service applications, creating
ms.assetid: 3abbb2ec-78d2-41e6-b9f9-6662d4e2cdc7
ms.openlocfilehash: cd749d325bec6636243dec1905f79abb5e42f04e
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608404"
---
# <a name="how-to-write-services-programmatically"></a><span data-ttu-id="16ab1-103">Практическое руководство. Создание службы программным способом</span><span class="sxs-lookup"><span data-stu-id="16ab1-103">How to: Write Services Programmatically</span></span>
<span data-ttu-id="16ab1-104">Если вы решили не использовать шаблон проекта "Служба Windows", для создания собственной службы вам придется настроить наследование и другие элементы инфраструктуры самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="16ab1-104">If you choose not to use the Windows Service project template, you can write your own services by setting up the inheritance and other infrastructure elements yourself.</span></span> <span data-ttu-id="16ab1-105">Создавая службу программным способом, вам необходимо выполнить несколько действий, которые в случае с шаблоном выполняются автоматически.</span><span class="sxs-lookup"><span data-stu-id="16ab1-105">When you create a service programmatically, you must perform several steps that the template would otherwise handle for you:</span></span>  
  
- <span data-ttu-id="16ab1-106">Для класса службы необходимо настроить наследование от класса <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="16ab1-106">You must set up your service class to inherit from the <xref:System.ServiceProcess.ServiceBase> class.</span></span>  
  
- <span data-ttu-id="16ab1-107">Для проекта службы необходимо создать метод `Main`, который определяет запускаемые службы и вызывает для них метод <xref:System.ServiceProcess.ServiceBase.Run%2A>.</span><span class="sxs-lookup"><span data-stu-id="16ab1-107">You must create a `Main` method for your service project that defines the services to run and calls the <xref:System.ServiceProcess.ServiceBase.Run%2A> method on them.</span></span>  
  
- <span data-ttu-id="16ab1-108">Необходимо переопределить процедуры <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и <xref:System.ServiceProcess.ServiceBase.OnStop%2A> и добавить код, который они должны выполнять.</span><span class="sxs-lookup"><span data-stu-id="16ab1-108">You must override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures and fill in any code you want them to run.</span></span>  
  
### <a name="to-write-a-service-programmatically"></a><span data-ttu-id="16ab1-109">Создание службы программным способом</span><span class="sxs-lookup"><span data-stu-id="16ab1-109">To write a service programmatically</span></span>  
  
1. <span data-ttu-id="16ab1-110">Создайте пустой проект, а затем создайте ссылку на необходимые пространства имен.</span><span class="sxs-lookup"><span data-stu-id="16ab1-110">Create an empty project and create a reference to the necessary namespaces by following these steps:</span></span>  
  
    1. <span data-ttu-id="16ab1-111">В окне **Обозреватель решений** щелкните правой кнопкой мыши узел **Ссылки** и выберите пункт **Добавить ссылку**.</span><span class="sxs-lookup"><span data-stu-id="16ab1-111">In **Solution Explorer**, right-click the **References** node and click **Add Reference**.</span></span>  
  
    2. <span data-ttu-id="16ab1-112">На вкладке **.NET Framework** найдите **System.dll** и щелкните **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="16ab1-112">On the **.NET Framework** tab, scroll to **System.dll** and click **Select**.</span></span>  
  
    3. <span data-ttu-id="16ab1-113">Найдите **System.ServiceProcess.dll** и щелкните **Выбрать**.</span><span class="sxs-lookup"><span data-stu-id="16ab1-113">Scroll to **System.ServiceProcess.dll** and click **Select**.</span></span>  
  
    4. <span data-ttu-id="16ab1-114">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="16ab1-114">Click **OK**.</span></span>  
  
2. <span data-ttu-id="16ab1-115">Добавьте класс и настройте для него наследование от <xref:System.ServiceProcess.ServiceBase>.</span><span class="sxs-lookup"><span data-stu-id="16ab1-115">Add a class and configure it to inherit from <xref:System.ServiceProcess.ServiceBase>:</span></span>  
  
     [!code-csharp[VbRadconService#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#7)]
     [!code-vb[VbRadconService#7](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#7)]  
  
3. <span data-ttu-id="16ab1-116">Настройте класс службы, добавив следующий код:</span><span class="sxs-lookup"><span data-stu-id="16ab1-116">Add the following code to configure your service class:</span></span>  
  
     [!code-csharp[VbRadconService#8](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#8)]
     [!code-vb[VbRadconService#8](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#8)]  
  
4. <span data-ttu-id="16ab1-117">Создайте для класса метод `Main` и с его помощью определите службы, которые будет содержать класс. `userService1` — имя класса.</span><span class="sxs-lookup"><span data-stu-id="16ab1-117">Create a `Main` method for your class, and use it to define the service your class will contain; `userService1` is the name of the class:</span></span>  
  
     [!code-csharp[VbRadconService#9](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#9)]
     [!code-vb[VbRadconService#9](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#9)]  
  
5. <span data-ttu-id="16ab1-118">Переопределите метод <xref:System.ServiceProcess.ServiceBase.OnStart%2A> и укажите обработку, которая должна выполняться при запуске службы.</span><span class="sxs-lookup"><span data-stu-id="16ab1-118">Override the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, and define any processing you want to occur when your service is started.</span></span>  
  
     [!code-csharp[VbRadconService#10](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#10)]
     [!code-vb[VbRadconService#10](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#10)]  
  
6. <span data-ttu-id="16ab1-119">Переопределите все прочие методы, для которых нужно задать определенную обработку, и напишите код, благодаря которому служба будет понимать, что нужно делать в каждом случае.</span><span class="sxs-lookup"><span data-stu-id="16ab1-119">Override any other methods you want to define custom processing for, and write code to determine the actions the service should take in each case.</span></span>  
  
7. <span data-ttu-id="16ab1-120">Добавить установщики, необходимые для приложения службы.</span><span class="sxs-lookup"><span data-stu-id="16ab1-120">Add the necessary installers for your service application.</span></span> <span data-ttu-id="16ab1-121">Дополнительные сведения см. в разделе [Практическое руководство. Добавление установщиков в приложение-службу](how-to-add-installers-to-your-service-application.md).</span><span class="sxs-lookup"><span data-stu-id="16ab1-121">For more information, see [How to: Add Installers to Your Service Application](how-to-add-installers-to-your-service-application.md).</span></span>  
  
8. <span data-ttu-id="16ab1-122">Скомпилируйте проект, выбрав в меню **Сборка** пункт **Собрать решение**.</span><span class="sxs-lookup"><span data-stu-id="16ab1-122">Build your project by selecting **Build Solution** from the **Build** menu.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="16ab1-123">Не нажимайте клавишу F5 для запуска проекта — таким способом нельзя запустить проект службы.</span><span class="sxs-lookup"><span data-stu-id="16ab1-123">Do not press F5 to run your project — you cannot run a service project in this way.</span></span>  
  
9. <span data-ttu-id="16ab1-124">Создайте проект установки и настраиваемые действия для установки службы.</span><span class="sxs-lookup"><span data-stu-id="16ab1-124">Create a setup project and the custom actions to install your service.</span></span> <span data-ttu-id="16ab1-125">Пример см. в разделе [Пошаговое руководство. Создание приложения служб Windows в конструкторе компонентов](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span><span class="sxs-lookup"><span data-stu-id="16ab1-125">For an example, see [Walkthrough: Creating a Windows Service Application in the Component Designer](walkthrough-creating-a-windows-service-application-in-the-component-designer.md).</span></span>  
  
10. <span data-ttu-id="16ab1-126">Установите службу.</span><span class="sxs-lookup"><span data-stu-id="16ab1-126">Install the service.</span></span> <span data-ttu-id="16ab1-127">Дополнительные сведения см. в разделе [Практическое руководство. Установка и удаление служб](how-to-install-and-uninstall-services.md).</span><span class="sxs-lookup"><span data-stu-id="16ab1-127">For more information, see [How to: Install and Uninstall Services](how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16ab1-128">См. также</span><span class="sxs-lookup"><span data-stu-id="16ab1-128">See also</span></span>

- [<span data-ttu-id="16ab1-129">Знакомство с приложениями служб Windows</span><span class="sxs-lookup"><span data-stu-id="16ab1-129">Introduction to Windows Service Applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="16ab1-130">Практическое руководство. Создание служб Windows</span><span class="sxs-lookup"><span data-stu-id="16ab1-130">How to: Create Windows Services</span></span>](how-to-create-windows-services.md)
- [<span data-ttu-id="16ab1-131">Практическое руководство. Добавление установщиков в приложение-службу</span><span class="sxs-lookup"><span data-stu-id="16ab1-131">How to: Add Installers to Your Service Application</span></span>](how-to-add-installers-to-your-service-application.md)
- [<span data-ttu-id="16ab1-132">Практическое руководство. Запись сведений о службах в журнал</span><span class="sxs-lookup"><span data-stu-id="16ab1-132">How to: Log Information About Services</span></span>](how-to-log-information-about-services.md)
- [<span data-ttu-id="16ab1-133">Пошаговое руководство: Создание приложения служб Windows в конструкторе компонентов</span><span class="sxs-lookup"><span data-stu-id="16ab1-133">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>](walkthrough-creating-a-windows-service-application-in-the-component-designer.md)
