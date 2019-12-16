---
title: "Windows Forms основы разработки приложений (Visual Basic) | Документы Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 22e8e38f56299250f485106bc65f3efb88485a42
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="windows-forms-application-basics-visual-basic"></a><span data-ttu-id="49205-102">Основы разработки приложений Windows Forms (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49205-102">Windows Forms Application Basics (Visual Basic)</span></span>
<span data-ttu-id="49205-103">Важной частью [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] является возможность создания приложений Windows Forms, локально работающих на компьютерах пользователей.</span><span class="sxs-lookup"><span data-stu-id="49205-103">An important part of [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] is the ability to create Windows Forms applications that run locally on users' computers.</span></span> <span data-ttu-id="49205-104">Visual Studio можно использовать для создания приложений и пользовательский интерфейс, с помощью Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="49205-104">You can use Visual Studio to create the application and user interface using Windows Forms.</span></span> <span data-ttu-id="49205-105">Приложение Windows Forms строится на основе классов из <xref:System.Windows.Forms>имен.</xref:System.Windows.Forms></span><span class="sxs-lookup"><span data-stu-id="49205-105">A Windows Forms application is built on classes from the <xref:System.Windows.Forms> namespace.</span></span>  
  
## <a name="designing-windows-forms-applications"></a><span data-ttu-id="49205-106">Разработка Windows Forms в приложения</span><span class="sxs-lookup"><span data-stu-id="49205-106">Designing Windows Forms Applications</span></span>  
 <span data-ttu-id="49205-107">Можно создать в Windows Forms и приложения служб Windows с [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].</span><span class="sxs-lookup"><span data-stu-id="49205-107">You can create Windows Forms and Windows service applications with [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)].</span></span> <span data-ttu-id="49205-108">Дополнительные сведения см. в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="49205-108">For more information, see the following topics:</span></span>  
  
-   <span data-ttu-id="49205-109">[Приступая к работе с Windows Forms](https://msdn.microsoft.com/library/ms229601.aspx).</span><span class="sxs-lookup"><span data-stu-id="49205-109">[Getting Started with Windows Forms](https://msdn.microsoft.com/library/ms229601.aspx).</span></span> <span data-ttu-id="49205-110">Сведения о создании и программировании Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="49205-110">Provides information on how to create and program Windows Forms.</span></span>  
   
-   <span data-ttu-id="49205-111">[Элементы управления Windows Forms](https://msdn.microsoft.com/library/ettb6e2a.aspx).</span><span class="sxs-lookup"><span data-stu-id="49205-111">[Windows Forms Controls](https://msdn.microsoft.com/library/ettb6e2a.aspx).</span></span> <span data-ttu-id="49205-112">Набор разделов, подробно описывающих использование элементов управления Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="49205-112">Collection of topics detailing the use of Windows Forms controls.</span></span>  
  
-   <span data-ttu-id="49205-113">[Приложения служб Windows](https://msdn.microsoft.com/library/y817hyb6.aspx).</span><span class="sxs-lookup"><span data-stu-id="49205-113">[Windows Service Applications](https://msdn.microsoft.com/library/y817hyb6.aspx).</span></span> <span data-ttu-id="49205-114">Список разделов, в которых описаны способы создания службы Windows.</span><span class="sxs-lookup"><span data-stu-id="49205-114">Lists topics that explain how to create Windows services.</span></span>  
  
## <a name="building-rich-interactive-user-interfaces"></a><span data-ttu-id="49205-115">Построение многофункциональных интерактивных пользовательских интерфейсов</span><span class="sxs-lookup"><span data-stu-id="49205-115">Building Rich, Interactive User Interfaces</span></span>  
 <span data-ttu-id="49205-116">Windows Forms — это компонент смарт клиентов [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], набор управляемых библиотек для выполнения распространенных задач, таких как чтение и запись в файловую систему.</span><span class="sxs-lookup"><span data-stu-id="49205-116">Windows Forms is the smart-client component of the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], a set of managed libraries that enable common application tasks such as reading and writing to the file system.</span></span> <span data-ttu-id="49205-117">В среде разработки, такие как [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], можно создавать приложения Windows Forms, которые отображают информацию, запрашивают ввод от пользователей и взаимодействия с удаленными компьютерами по сети.</span><span class="sxs-lookup"><span data-stu-id="49205-117">Using a development environment like [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], you can create Windows Forms applications that display information, request input from users, and communicate with remote computers over a network.</span></span>  
  
 <span data-ttu-id="49205-118">В Windows Forms форма является видимая поверхность, на которой отображается информация для пользователя.</span><span class="sxs-lookup"><span data-stu-id="49205-118">In Windows Forms, a form is a visual surface on which you display information to the user.</span></span> <span data-ttu-id="49205-119">Обычно создание приложений Windows Forms путем размещения элементов управления в формах и разработки ответов на действия пользователя, такие как щелчки мыши или нажатия клавиш.</span><span class="sxs-lookup"><span data-stu-id="49205-119">You commonly build Windows Forms applications by placing controls on forms and developing responses to user actions, such as mouse clicks or key presses.</span></span> <span data-ttu-id="49205-120">Объект *управления* — отдельный элемент (UI), предназначенный для отображения или ввода данных.</span><span class="sxs-lookup"><span data-stu-id="49205-120">A *control* is a discrete user interface (UI) element that displays data or accepts data input.</span></span>  
  
### <a name="events"></a><span data-ttu-id="49205-121">События</span><span class="sxs-lookup"><span data-stu-id="49205-121">Events</span></span>  
 <span data-ttu-id="49205-122">Когда пользователь выполняет что-то с формой или одним из ее элементов управления, создается событие.</span><span class="sxs-lookup"><span data-stu-id="49205-122">When a user does something to your form or one of its controls, it generates an event.</span></span> <span data-ttu-id="49205-123">Приложение реагирует на эти события с помощью кода и обрабатывает события при их возникновении.</span><span class="sxs-lookup"><span data-stu-id="49205-123">Your application reacts to these events by using code, and processes the events when they occur.</span></span> <span data-ttu-id="49205-124">Дополнительные сведения см. в разделе [Создание обработчиков событий в Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx).</span><span class="sxs-lookup"><span data-stu-id="49205-124">For more information, see [Creating Event Handlers in Windows Forms](https://msdn.microsoft.com/library/dacysss4.aspx).</span></span>  
  
### <a name="controls"></a><span data-ttu-id="49205-125">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="49205-125">Controls</span></span>  
 <span data-ttu-id="49205-126">Windows Forms включает широкий набор элементов управления, которые можно помещать на формы: элементы управления, отображающие текстовые поля, кнопки, раскрывающиеся списки, переключатели и даже веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="49205-126">Windows Forms contains a variety of controls that you can place on forms: controls that display text boxes, buttons, drop-down boxes, radio buttons, and even Web pages.</span></span> <span data-ttu-id="49205-127">Список всех элементов управления, которые можно использовать в форме, в разделе [элементы управления для использования в формах Windows Forms](https://msdn.microsoft.com/library/3xdhey7w.aspx).</span><span class="sxs-lookup"><span data-stu-id="49205-127">For a list of all the controls you can use on a form, see [Controls to Use on Windows Forms](https://msdn.microsoft.com/library/3xdhey7w.aspx).</span></span> <span data-ttu-id="49205-128">Если существующий элемент управления не удовлетворяет потребностям, Windows Forms можно создавать собственные пользовательские элементы управления с помощью <xref:System.Windows.Forms.UserControl>класса.</xref:System.Windows.Forms.UserControl></span><span class="sxs-lookup"><span data-stu-id="49205-128">If an existing control does not meet your needs, Windows Forms also supports creating your own custom controls using the <xref:System.Windows.Forms.UserControl> class.</span></span>  
  
 <span data-ttu-id="49205-129">В состав Windows Forms входят многофункциональные элементы пользовательского интерфейса, позволяющие воссоздавать возможности таких сложных приложений, как Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="49205-129">Windows Forms has rich UI controls that emulate features in high-end applications like Microsoft Office.</span></span> <span data-ttu-id="49205-130">С помощью <xref:System.Windows.Forms.ToolStrip>и <xref:System.Windows.Forms.MenuStrip>элемента управления, можно создать панели инструментов и меню, содержащие текст и изображения, показывать подменю и размещать другие элементы, такие как текстовые поля и поля со списком.</xref:System.Windows.Forms.MenuStrip> </xref:System.Windows.Forms.ToolStrip></span><span class="sxs-lookup"><span data-stu-id="49205-130">Using the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip> control, you can create toolbars and menus that contain text and images, display submenus, and host other controls such as text boxes and combo boxes.</span></span>  
  
 <span data-ttu-id="49205-131">С [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] конструктор форм и перетащите можно легко создавать приложения Windows Forms: достаточно выделить элементы управления курсором и поместить их в нужное место на форме.</span><span class="sxs-lookup"><span data-stu-id="49205-131">With the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] drag-and-drop forms designer, you can easily create Windows Forms applications: just select the controls with your cursor and place them where you want on the form.</span></span> <span data-ttu-id="49205-132">Конструктор предоставляет средства, такие как линии сетки и «линии привязки» для преодоления трудностей выравнивания элементов управления.</span><span class="sxs-lookup"><span data-stu-id="49205-132">The designer provides tools such as grid lines and "snap lines" to take the hassle out of aligning controls.</span></span> <span data-ttu-id="49205-133">И при использовании [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] и при компиляции из командной строки можно использовать <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel>и <xref:System.Windows.Forms.SplitContainer>форме элементы управления для создания сложных макетов с минимальными затратами времени и усилий.</xref:System.Windows.Forms.SplitContainer> </xref:System.Windows.Forms.TableLayoutPanel> </xref:System.Windows.Forms.FlowLayoutPanel></span><span class="sxs-lookup"><span data-stu-id="49205-133">And whether you use [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] or compile at the command line, you can use the <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> and <xref:System.Windows.Forms.SplitContainer> controls to create advanced form layouts with minimal time and effort.</span></span>  
  
### <a name="custom-ui-elements"></a><span data-ttu-id="49205-134">Элементы пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="49205-134">Custom UI Elements</span></span>  
 <span data-ttu-id="49205-135">Наконец, если необходимо создать собственные настраиваемые элементы пользовательского интерфейса <xref:System.Drawing>пространство имен содержит все классы, необходимые для отображения линий, кругов и других фигур непосредственно на форме.</xref:System.Drawing></span><span class="sxs-lookup"><span data-stu-id="49205-135">Finally, if you must create your own custom UI elements, the <xref:System.Drawing> namespace contains all of the classes you need to render lines, circles, and other shapes directly on a form.</span></span>  
  
 <span data-ttu-id="49205-136">Пошаговые инструкции по использованию этих функций см. в следующих разделах справки.</span><span class="sxs-lookup"><span data-stu-id="49205-136">For step-by-step information about using these features, see the following Help topics.</span></span>  
  
|<span data-ttu-id="49205-137">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="49205-137">To</span></span>|<span data-ttu-id="49205-138">См.</span><span class="sxs-lookup"><span data-stu-id="49205-138">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="49205-139">Создание нового приложения Windows Forms с помощью[!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]</span><span class="sxs-lookup"><span data-stu-id="49205-139">Create a new Windows Forms application with [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]</span></span>|[<span data-ttu-id="49205-140">Пошаговое руководство: Создание простого Windows Form</span><span class="sxs-lookup"><span data-stu-id="49205-140">Walkthrough: Creating a Simple Windows Form</span></span>](http://msdn.microsoft.com/en-us/2d9daec0-0543-41d0-acb1-964f685bddbb)|  
|<span data-ttu-id="49205-141">Использование элементов управления в формах</span><span class="sxs-lookup"><span data-stu-id="49205-141">Use controls on forms</span></span>|[<span data-ttu-id="49205-142">Практическое руководство: Добавление элементов управления в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49205-142">How to: Add Controls to Windows Forms</span></span>](https://msdn.microsoft.com/library/0h5y8567.aspx)|   
|<span data-ttu-id="49205-143">Создание рисунков с помощью<xref:System.Drawing></xref:System.Drawing></span><span class="sxs-lookup"><span data-stu-id="49205-143">Create graphics with <xref:System.Drawing></span></span>|[<span data-ttu-id="49205-144">Приступая к программированию графики</span><span class="sxs-lookup"><span data-stu-id="49205-144">Getting Started with Graphics Programming</span></span>](https://msdn.microsoft.com/library/da0f23z7.aspx)|  
|<span data-ttu-id="49205-145">Создание пользовательских элементов управления</span><span class="sxs-lookup"><span data-stu-id="49205-145">Create custom controls</span></span>|[<span data-ttu-id="49205-146">Практическое руководство: наследование класса UserControl</span><span class="sxs-lookup"><span data-stu-id="49205-146">How to: Inherit from the UserControl Class</span></span>](https://msdn.microsoft.com/library/00ctb4z0.aspx)|  
  
## <a name="displaying-and-manipulating-data"></a><span data-ttu-id="49205-147">Отображение и обработка данных</span><span class="sxs-lookup"><span data-stu-id="49205-147">Displaying and Manipulating Data</span></span>  
 <span data-ttu-id="49205-148">Во многих приложениях нужно отображать данные из базы данных, XML-файла, веб-службы XML или другого источника данных.</span><span class="sxs-lookup"><span data-stu-id="49205-148">Many applications must display data from a database, XML file, XML Web service, or other data source.</span></span> <span data-ttu-id="49205-149">Windows Forms предоставляет гибкий элемент управления с именем <xref:System.Windows.Forms.DataGridView>, предназначенный для представления таких табличных данных в традиционном формате строк и столбцов так, что каждый фрагмент данных занимает свою собственную ячейку.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="49205-149">Windows Forms provides a flexible control called the <xref:System.Windows.Forms.DataGridView> control for rendering such tabular data in a traditional row and column format, so that every piece of data occupies its own cell.</span></span> <span data-ttu-id="49205-150">С помощью <xref:System.Windows.Forms.DataGridView>можно настроить внешний вид отдельных ячеек, зафиксировать строки и столбцы на своем месте и отображение сложных элементов управления внутри ячеек, помимо других функций.</xref:System.Windows.Forms.DataGridView></span><span class="sxs-lookup"><span data-stu-id="49205-150">Using <xref:System.Windows.Forms.DataGridView> you can customize the appearance of individual cells, lock arbitrary rows and columns in place, and display complex controls inside cells, among other features.</span></span>  
  
 <span data-ttu-id="49205-151">При использовании интеллектуальных клиентов Windows Forms можно легко подключаться к источникам данных по сети.</span><span class="sxs-lookup"><span data-stu-id="49205-151">Connecting to data sources over a network is a simple task with Windows Forms smart clients.</span></span> <span data-ttu-id="49205-152"><xref:System.Windows.Forms.BindingSource>Компонент, появившееся в Windows Forms в [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] и [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)], представляет собой соединение с источником данных и предоставляет методы для привязки данных к элементам управления, перехода к предыдущей и следующей записи, редактирования записей и сохранения изменений в исходном источнике.</xref:System.Windows.Forms.BindingSource></span><span class="sxs-lookup"><span data-stu-id="49205-152">The <xref:System.Windows.Forms.BindingSource> component, new with Windows Forms in [!INCLUDE[vsprvslong](../../../csharp/misc/includes/vsprvslong_md.md)] and the [!INCLUDE[dnprdnlong](../../../csharp/programming-guide/events/includes/dnprdnlong_md.md)], represents a connection to a data source, and exposes methods for binding data to controls, navigating to the previous and next records, editing records, and saving changes back to the original source.</span></span> <span data-ttu-id="49205-153"><xref:System.Windows.Forms.BindingNavigator>Управления предоставляет простой интерфейс на <xref:System.Windows.Forms.BindingSource>компонента для перехода между записями.</xref:System.Windows.Forms.BindingSource> </xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="49205-153">The <xref:System.Windows.Forms.BindingNavigator> control provides a simple interface over the <xref:System.Windows.Forms.BindingSource> component for users to navigate between records.</span></span>  
  
### <a name="data-bound-controls"></a><span data-ttu-id="49205-154">Элементы управления с привязкой к данным</span><span class="sxs-lookup"><span data-stu-id="49205-154">Data-Bound Controls</span></span>  
 <span data-ttu-id="49205-155">Можно создать элементы управления с привязкой к данным с помощью окна "Источники данных", отображающий источников данных, таких как базы данных, веб-службы и объекты в проекте.</span><span class="sxs-lookup"><span data-stu-id="49205-155">You can create data-bound controls easily using the Data Sources window, which displays data sources such as databases, Web services, and objects in your project.</span></span> <span data-ttu-id="49205-156">Создавать элементы управления с привязкой к данным можно путем перетаскивания объектов из этого окна в формы проекта.</span><span class="sxs-lookup"><span data-stu-id="49205-156">You can create data-bound controls by dragging items from this window onto forms in your project.</span></span> <span data-ttu-id="49205-157">Также можно связывать существующие элементы управления с данными, перетаскивая объекты из окна "Источники данных" в существующие элементы управления.</span><span class="sxs-lookup"><span data-stu-id="49205-157">You can also data-bind existing controls to data by dragging objects from the Data Sources window onto existing controls.</span></span>  
  
### <a name="settings"></a><span data-ttu-id="49205-158">Параметры</span><span class="sxs-lookup"><span data-stu-id="49205-158">Settings</span></span>  
 <span data-ttu-id="49205-159">Другой тип привязки данных, которыми можно управлять в Windows Forms — это параметры.</span><span class="sxs-lookup"><span data-stu-id="49205-159">Another type of data binding you can manage in Windows Forms is settings.</span></span> <span data-ttu-id="49205-160">Большинство приложений интеллектуальных клиентов должны сохранять некоторые сведения о своем состоянии во время выполнения, например последний известный размер форм и сохранять пользовательские настройки, например расположение сохраняемых файлов по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="49205-160">Most smart-client applications must retain some information about their run-time state, such as the last-known size of forms, and retain user-preference data, such as default locations for saved files.</span></span> <span data-ttu-id="49205-161">Параметры приложения отвечает этим требованиям, предоставляя простой способ хранения обоих типов параметров на клиентском компьютере.</span><span class="sxs-lookup"><span data-stu-id="49205-161">The application-settings feature addresses these requirements by providing an easy way to store both types of settings on the client computer.</span></span> <span data-ttu-id="49205-162">Определенные один раз с помощью [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] или редактора кода, эти параметры сохраняются в XML-ФАЙЛЕ и автоматически считываются обратно в память во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="49205-162">Once defined using either [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] or a code editor, these settings are persisted as XML and automatically read back into memory at run time.</span></span>  
  
 <span data-ttu-id="49205-163">Пошаговые инструкции по использованию этих функций см. в следующих разделах справки.</span><span class="sxs-lookup"><span data-stu-id="49205-163">For step-by-step information about using these features, see the following Help topics.</span></span>  
  
|<span data-ttu-id="49205-164">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="49205-164">To</span></span>|<span data-ttu-id="49205-165">См.</span><span class="sxs-lookup"><span data-stu-id="49205-165">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="49205-166">Использование <xref:System.Windows.Forms.BindingSource>компонента</xref:System.Windows.Forms.BindingSource></span><span class="sxs-lookup"><span data-stu-id="49205-166">Use the <xref:System.Windows.Forms.BindingSource> component</span></span>|[<span data-ttu-id="49205-167">Практическое руководство: привязка элементов управления Windows Forms с компонентом BindingSource с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="49205-167">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>](https://msdn.microsoft.com/library/801dxw2t.aspx)|  
|<span data-ttu-id="49205-168">Работа с [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] источников данных</span><span class="sxs-lookup"><span data-stu-id="49205-168">Work with [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] data sources</span></span>|[<span data-ttu-id="49205-169">Практическое руководство: сортировка и фильтрация данных ADO.NET с помощью компонента BindingSource в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49205-169">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](https://msdn.microsoft.com/library/ya3sah92.aspx)|  
|<span data-ttu-id="49205-170">Использование окна источников данных</span><span class="sxs-lookup"><span data-stu-id="49205-170">Use the Data Sources window</span></span>|[<span data-ttu-id="49205-171">Пошаговое руководство. Отображение данных на форме в приложении Windows</span><span class="sxs-lookup"><span data-stu-id="49205-171">Walkthrough: Displaying Data on a Windows Form</span></span>](https://docs.microsoft.com/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a><span data-ttu-id="49205-172">Развертывание приложений на клиентских компьютерах</span><span class="sxs-lookup"><span data-stu-id="49205-172">Deploying Applications to Client Computers</span></span>  
 <span data-ttu-id="49205-173">После написания приложения необходимо отправить его пользователям, чтобы они могли установить и запустить его на своих клиентских компьютерах.</span><span class="sxs-lookup"><span data-stu-id="49205-173">Once you have written your application, you must send it to your users so that they can install and run it on their own client computers.</span></span> <span data-ttu-id="49205-174">С помощью [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] технологии, можно развернуть приложение из среды [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] , используя всего несколько щелчков и предоставлять пользователям URL-адрес приложения в Интернете.</span><span class="sxs-lookup"><span data-stu-id="49205-174">Using the [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] technology, you can deploy your applications from within [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] by using just a few clicks and provide users with a URL pointing to your application on the Web.</span></span> [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]<span data-ttu-id="49205-175">управляет всеми элементами и зависимостями в приложении и обеспечивает установку приложения на клиентском компьютере должным образом.</span><span class="sxs-lookup"><span data-stu-id="49205-175"> manages all of the elements and dependencies in your application and ensures that the application is properly installed on the client computer.</span></span>  
  
 <span data-ttu-id="49205-176">Приложения [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] можно настроить так, чтобы они работали только при подключении к сети или как в сетевом, так и в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="49205-176">[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] applications can be configured to run only when the user is connected to the network, or to run both online and offline.</span></span> <span data-ttu-id="49205-177">При указании, что приложение должно поддерживать операции в автономном режиме, [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] добавляет ссылку на приложение в каталоге пользователя **запустить** меню, так что пользователь сможет открыть его без использования URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="49205-177">When you specify that an application should support offline operation, [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] adds a link to your application in the user's **Start** menu, so that the user can open it without using the URL.</span></span>  
  
 <span data-ttu-id="49205-178">Когда вы обновляете приложение, на веб-сервере публикуется новый манифест развертывания и новая копия приложения.</span><span class="sxs-lookup"><span data-stu-id="49205-178">When you update your application, you publish a new deployment manifest and a new copy of your application to your Web server.</span></span> [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]<span data-ttu-id="49205-179">обнаруживает наличие обновлений и обновляет пакет установки пользователя; требуется никакого программирования для обновления старых сборок.</span><span class="sxs-lookup"><span data-stu-id="49205-179"> detects that there is an update available and upgrades the user's installation; no custom programming is required to update old assemblies.</span></span>  
  
 <span data-ttu-id="49205-180">Полное описание [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)], в разделе [развертывание и безопасность технологии ClickOnce](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="49205-180">For a full introduction to [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)], see [ClickOnce Security and Deployment](https://docs.microsoft.com/visualstudio/deployment/clickonce-security-and-deployment).</span></span> <span data-ttu-id="49205-181">Пошаговые инструкции по использованию этих функций см. в следующих разделах справки:</span><span class="sxs-lookup"><span data-stu-id="49205-181">For step-by-step information about using these features, see the following Help topics:</span></span>  
  
|<span data-ttu-id="49205-182">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="49205-182">To</span></span>|<span data-ttu-id="49205-183">См.</span><span class="sxs-lookup"><span data-stu-id="49205-183">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="49205-184">Развертывание приложения с[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]</span><span class="sxs-lookup"><span data-stu-id="49205-184">Deploy an application with [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]</span></span>|[<span data-ttu-id="49205-185">Практическое руководство. Публикация приложения ClickOnce с помощью мастера публикации</span><span class="sxs-lookup"><span data-stu-id="49205-185">How to: Publish a ClickOnce Application using the Publish Wizard</span></span>](https://docs.microsoft.com/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [<span data-ttu-id="49205-186">Разбор примера: развертывание вручную приложения ClickOnce</span><span class="sxs-lookup"><span data-stu-id="49205-186">Walkthrough: Manually Deploying a ClickOnce Application</span></span>](https://docs.microsoft.com/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|<span data-ttu-id="49205-187">Обновление [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] развертывания</span><span class="sxs-lookup"><span data-stu-id="49205-187">Update a [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)] deployment</span></span>|[<span data-ttu-id="49205-188">Практическое руководство. Управление обновлениями для ClickOnce-приложения</span><span class="sxs-lookup"><span data-stu-id="49205-188">How to: Manage Updates for a ClickOnce Application</span></span>](https://docs.microsoft.com/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|<span data-ttu-id="49205-189">Управление безопасностью с помощью[!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]</span><span class="sxs-lookup"><span data-stu-id="49205-189">Manage security with [!INCLUDE[ndptecclick](../../../visual-basic/developing-apps/printing/includes/ndptecclick_md.md)]</span></span>|[<span data-ttu-id="49205-190">Практическое руководство. Включение параметров безопасности ClickOnce-приложений</span><span class="sxs-lookup"><span data-stu-id="49205-190">How to: Enable ClickOnce Security Settings</span></span>](https://docs.microsoft.com/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a><span data-ttu-id="49205-191">Другие элементы управления и возможности</span><span class="sxs-lookup"><span data-stu-id="49205-191">Other Controls and Features</span></span>  
 <span data-ttu-id="49205-192">В Windows Forms имеется множество других возможностей, которые упрощают и ускоряют реализацию общих задач, таких как создание диалоговых окон, печать, добавление справки и документации, а также локализация приложений на различных языках.</span><span class="sxs-lookup"><span data-stu-id="49205-192">There are many other features in Windows Forms that make implementing common tasks fast and easy, such as support for creating dialog boxes, printing, adding Help and documentation, and localizing your application to multiple languages.</span></span> <span data-ttu-id="49205-193">Кроме того, Windows Forms применяется эффективная система безопасности [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], позволяя предоставить заказчикам более защищенные приложения.</span><span class="sxs-lookup"><span data-stu-id="49205-193">In addition, Windows Forms relies on the robust security system of the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)], enabling you to release more secure applications to your customers.</span></span>  
  
 <span data-ttu-id="49205-194">Пошаговые инструкции по использованию этих функций см. в следующих разделах справки:</span><span class="sxs-lookup"><span data-stu-id="49205-194">For step-by-step information about using these features, see the following Help topics:</span></span>  
  
|<span data-ttu-id="49205-195">Целевой тип</span><span class="sxs-lookup"><span data-stu-id="49205-195">To</span></span>|<span data-ttu-id="49205-196">См.</span><span class="sxs-lookup"><span data-stu-id="49205-196">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="49205-197">Печать содержимого формы</span><span class="sxs-lookup"><span data-stu-id="49205-197">Print the contents of a form</span></span>|[<span data-ttu-id="49205-198">Практическое руководство: печать графических изображений в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49205-198">How to: Print Graphics in Windows Forms</span></span>](https://msdn.microsoft.com/library/741a0ktc.aspx)<br /><br /> [<span data-ttu-id="49205-199">Практическое руководство: печать многостраничных текстовых файлов в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49205-199">How to: Print a Multi-Page Text File in Windows Forms</span></span>](https://msdn.microsoft.com/library/cwbe712d.aspx)|   
|<span data-ttu-id="49205-200">Дополнительные сведения о безопасности форм Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49205-200">Learn more about Windows Forms security</span></span>|[<span data-ttu-id="49205-201">Безопасность в Windows Forms Overview</span><span class="sxs-lookup"><span data-stu-id="49205-201">Security in Windows Forms Overview</span></span>](https://msdn.microsoft.com/library/90k49ccb.aspx)|  
  
## <a name="see-also"></a><span data-ttu-id="49205-202">См. также</span><span class="sxs-lookup"><span data-stu-id="49205-202">See Also</span></span>  
 <span data-ttu-id="49205-203"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></span><span class="sxs-lookup"><span data-stu-id="49205-203"><xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase></span></span>   
<span data-ttu-id="49205-204"> [Общие сведения о Windows Forms](https://msdn.microsoft.com/library/8bxxy49h.aspx) </span><span class="sxs-lookup"><span data-stu-id="49205-204"> [Windows Forms Overview](https://msdn.microsoft.com/library/8bxxy49h.aspx) </span></span>  
<span data-ttu-id="49205-205"> [Объект My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md)</span><span class="sxs-lookup"><span data-stu-id="49205-205"> [My.Forms Object](../../../visual-basic/language-reference/objects/my-forms-object.md)</span></span>