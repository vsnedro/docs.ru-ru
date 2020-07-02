---
title: Введение в WPF
titleSuffix: ''
description: Создавайте визуально привлекательные пользовательские интерфейсы в Windows. Ознакомьтесь с основными возможностями и концепциями Windows Presentation Foundation (WPF).
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b8d7cf43-d1f2-4f3d-adb0-4f3a6428edc0
dev_langs:
- csharp
- vb
ms.openlocfilehash: 7a79174f5f3aebe90190db45566b37bd5e9fbe3f
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853583"
---
# <a name="wpf-overview"></a><span data-ttu-id="e38a3-104">Общие сведения о WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-104">WPF overview</span></span>

<span data-ttu-id="e38a3-105">Платформа Windows Presentation Foundation (WPF) позволяет создавать клиентские приложения для настольных систем Windows с привлекательным пользовательским интерфейсом.</span><span class="sxs-lookup"><span data-stu-id="e38a3-105">Windows Presentation Foundation (WPF) lets you create desktop client applications for Windows with visually stunning user experiences.</span></span>

![Пример пользовательского интерфейса Contoso Healthcare](media/introduction-to-wpf/wpfintrofigure24.png)

<span data-ttu-id="e38a3-107">В основе WPF лежит независимый от разрешения векторный модуль визуализации, использующий возможности современного графического оборудования.</span><span class="sxs-lookup"><span data-stu-id="e38a3-107">The core of WPF is a resolution-independent and vector-based rendering engine that is built to take advantage of modern graphics hardware.</span></span> <span data-ttu-id="e38a3-108">Возможности этого модуля расширяются с помощью комплексного набора функций разработки приложений, которые включают в себя язык XAML, элементы управления, привязку к данным, макет, двумерную и трехмерную графику, анимацию, стили, шаблоны, документы, мультимедиа, текст и типографические функции.</span><span class="sxs-lookup"><span data-stu-id="e38a3-108">WPF extends the core with a comprehensive set of application-development features that include Extensible Application Markup Language (XAML), controls, data binding, layout, 2D and 3D graphics, animation, styles, templates, documents, media, text, and typography.</span></span> <span data-ttu-id="e38a3-109">WPF является частью .NET, поэтому вы можете создавать приложения, включающие другие элементы .NET API.</span><span class="sxs-lookup"><span data-stu-id="e38a3-109">WPF is part of .NET, so you can build applications that incorporate other elements of the .NET API.</span></span>

<span data-ttu-id="e38a3-110">Этот обзор предназначен для новичков: в нем рассматриваются ключевые возможности и понятия WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-110">This overview is intended for newcomers and covers the key capabilities and concepts of WPF.</span></span>

## <a name="program-with-wpf"></a><span data-ttu-id="e38a3-111">Программирование с помощью WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-111">Program with WPF</span></span>

<span data-ttu-id="e38a3-112">WPF существует в виде подмножества типов .NET, которые по большей части находятся в пространстве имен <xref:System.Windows>.</span><span class="sxs-lookup"><span data-stu-id="e38a3-112">WPF exists as a subset of .NET types that are (for the most part) located in the <xref:System.Windows> namespace.</span></span> <span data-ttu-id="e38a3-113">Если ранее вы создавали приложения с помощью .NET, используя управляемые технологии, такие как ASP.NET и Windows Forms, основные принципы программирования с помощью WPF должны быть вам знакомы: вы создаете экземпляры классов, задаете свойства, вызываете методы и обрабатываете события — все это с использованием своего любимого языка программирования .NET, например C# или Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e38a3-113">If you have previously built applications with .NET using managed technologies like ASP.NET and Windows Forms, the fundamental WPF programming experience should be familiar; you instantiate classes, set properties, call methods, and handle events, using your favorite .NET programming language, such as C# or Visual Basic.</span></span>

<span data-ttu-id="e38a3-114">WPF включает в себя дополнительные конструкции программирования, которые расширяют возможности свойств и событий: [свойства зависимостей](advanced/dependency-properties-overview.md) и [перенаправленные события](advanced/routed-events-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-114">WPF includes additional programming constructs that enhance properties and events: [dependency properties](advanced/dependency-properties-overview.md) and [routed events](advanced/routed-events-overview.md).</span></span>

## <a name="markup-and-code-behind"></a><span data-ttu-id="e38a3-115">Разметка и код программной части</span><span class="sxs-lookup"><span data-stu-id="e38a3-115">Markup and code-behind</span></span>

<span data-ttu-id="e38a3-116">WPF позволяет разрабатывать приложения, используя как *разметку*, так и *код программной части*, что привычно для разработчиков на ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="e38a3-116">WPF lets you develop an application using both *markup* and *code-behind*, an experience with which ASP.NET developers should be familiar.</span></span> <span data-ttu-id="e38a3-117">Разметка XAML обычно используется для определения внешнего вида приложения, а управляемые языки программирования (код программной части) — для реализации его поведения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-117">You generally use XAML markup to implement the appearance of an application while using managed programming languages (code-behind) to implement its behavior.</span></span> <span data-ttu-id="e38a3-118">Такое разделение внешнего вида и поведения имеет ряд преимуществ.</span><span class="sxs-lookup"><span data-stu-id="e38a3-118">This separation of appearance and behavior has the following benefits:</span></span>

- <span data-ttu-id="e38a3-119">Затраты на разработку и обслуживание снижаются, так как разметка, определяющая внешний вид, не связана тесно с кодом, обуславливающим поведение.</span><span class="sxs-lookup"><span data-stu-id="e38a3-119">Development and maintenance costs are reduced because appearance-specific markup is not tightly coupled with behavior-specific code.</span></span>

- <span data-ttu-id="e38a3-120">Повышается эффективность разработки, так как дизайнеры, занимающиеся внешним видом приложения, могут работать параллельно с разработчиками, реализующими поведение приложения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-120">Development is more efficient because designers can implement an application's appearance simultaneously with developers who are implementing the application's behavior.</span></span>

- <span data-ttu-id="e38a3-121">[Глобализация и локализация](advanced/wpf-globalization-and-localization-overview.md) приложений WPF упрощена.</span><span class="sxs-lookup"><span data-stu-id="e38a3-121">[Globalization and localization](advanced/wpf-globalization-and-localization-overview.md) for WPF applications is simplified.</span></span>

### <a name="markup"></a><span data-ttu-id="e38a3-122">разметку</span><span class="sxs-lookup"><span data-stu-id="e38a3-122">Markup</span></span>

<span data-ttu-id="e38a3-123">XAML — это язык разметки на основе XML, который служит для определения внешнего вида приложения в декларативной форме.</span><span class="sxs-lookup"><span data-stu-id="e38a3-123">XAML is an XML-based markup language that implements an application's appearance declaratively.</span></span> <span data-ttu-id="e38a3-124">Обычно он используется для создания окон, страниц и пользовательских элементов управления, а также их заполнения элементами управления, фигурами и графическими элементами.</span><span class="sxs-lookup"><span data-stu-id="e38a3-124">You typically use it to create windows, dialog boxes, pages, and user controls, and to fill them with controls, shapes, and graphics.</span></span>

<span data-ttu-id="e38a3-125">В следующем примере XAML используется для реализации внешнего вида окна, содержащего одну кнопку:</span><span class="sxs-lookup"><span data-stu-id="e38a3-125">The following example uses XAML to implement the appearance of a window that contains a single button:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

<span data-ttu-id="e38a3-126">Этот код XAML определяет окно и кнопку с помощью элементов `Window` и `Button` соответственно.</span><span class="sxs-lookup"><span data-stu-id="e38a3-126">Specifically, this XAML defines a window and a button by using the `Window` and `Button` elements, respectively.</span></span> <span data-ttu-id="e38a3-127">Каждый элемент настраивается с помощью атрибутов, например атрибута `Window` элемента `Title` , определяющего текст заголовка окна.</span><span class="sxs-lookup"><span data-stu-id="e38a3-127">Each element is configured with attributes, such as the `Window` element's `Title` attribute to specify the window's title-bar text.</span></span> <span data-ttu-id="e38a3-128">Во время выполнения WPF преобразует элементы и атрибуты, определенные в разметке, в экземпляры классов WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-128">At run time, WPF converts the elements and attributes that are defined in markup to instances of WPF classes.</span></span> <span data-ttu-id="e38a3-129">Например, элемент `Window` преобразуется в экземпляр класса <xref:System.Windows.Window> , свойство <xref:System.Windows.Window.Title%2A> которого является значением атрибута `Title` .</span><span class="sxs-lookup"><span data-stu-id="e38a3-129">For example, the `Window` element is converted to an instance of the <xref:System.Windows.Window> class whose <xref:System.Windows.Window.Title%2A> property is the value of the `Title` attribute.</span></span>

<span data-ttu-id="e38a3-130">На следующем рисунке показан пользовательский интерфейс, определяемый XAML в предыдущем примере:</span><span class="sxs-lookup"><span data-stu-id="e38a3-130">The following figure shows the user interface (UI) that is defined by the XAML in the previous example:</span></span>

![Окно с кнопкой](media/introduction-to-wpf/wpfintrofigure10.png)

<span data-ttu-id="e38a3-132">Так как язык XAML основан на XML, создаваемый с его помощью пользовательский интерфейс образует иерархию вложенных элементов, известную как [дерево элементов](advanced/trees-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-132">Since XAML is XML-based, the UI that you compose with it is assembled in a hierarchy of nested elements known as an [element tree](advanced/trees-in-wpf.md).</span></span> <span data-ttu-id="e38a3-133">Дерево элементов обеспечивает логичный и интуитивно понятный способ создания пользовательских интерфейсов и управления ими.</span><span class="sxs-lookup"><span data-stu-id="e38a3-133">The element tree provides a logical and intuitive way to create and manage UIs.</span></span>

### <a name="code-behind"></a><span data-ttu-id="e38a3-134">Файл с кодом программной части</span><span class="sxs-lookup"><span data-stu-id="e38a3-134">Code-behind</span></span>

<span data-ttu-id="e38a3-135">При разработке поведения приложения главной задачей является обеспечение реакции на действия пользователя, включая обработку событий (таких как выбор пункта меню или нажатие на кнопку), и вызов в ответ бизнес-логики и логики доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="e38a3-135">The main behavior of an application is to implement the functionality that responds to user interactions, including handling events (for example, clicking a menu, tool bar, or button) and calling business logic and data access logic in response.</span></span> <span data-ttu-id="e38a3-136">В WPF такое поведение реализуется в коде, связанном с разметкой.</span><span class="sxs-lookup"><span data-stu-id="e38a3-136">In WPF, this behavior is implemented in code that is associated with markup.</span></span> <span data-ttu-id="e38a3-137">Этот код называется кодом программной части.</span><span class="sxs-lookup"><span data-stu-id="e38a3-137">This type of code is known as code-behind.</span></span> <span data-ttu-id="e38a3-138">В следующем примере показана обновленная разметка из предыдущего примера и кода программной части:</span><span class="sxs-lookup"><span data-stu-id="e38a3-138">The following example shows the updated markup from the previous example and the code-behind:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.AWindow"
    Title="Window with Button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button" Click="button_Click">Click Me!</Button>

</Window>
```

```csharp
using System.Windows; // Window, RoutedEventArgs, MessageBox

namespace SDKSample
{
    public partial class AWindow : Window
    {
        public AWindow()
        {
            // InitializeComponent call is required to merge the UI
            // that is defined in markup with this class, including  
            // setting properties and registering event handlers
            InitializeComponent();
        }

        void button_Click(object sender, RoutedEventArgs e)
        {
            // Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!");
        }
    }
}
```

```vb
Namespace SDKSample

    Partial Public Class AWindow
        Inherits System.Windows.Window

        Public Sub New()

            ' InitializeComponent call is required to merge the UI
            ' that is defined in markup with this class, including  
            ' setting properties and registering event handlers
            InitializeComponent()

        End Sub

        Private Sub button_Click(ByVal sender As Object, ByVal e As RoutedEventArgs)

            ' Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!")

        End Sub

    End Class

End Namespace
```

<span data-ttu-id="e38a3-139">В этом примере в коде программной части реализован класс, производный от класса <xref:System.Windows.Window> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-139">In this example, the code-behind implements a class that derives from the <xref:System.Windows.Window> class.</span></span> <span data-ttu-id="e38a3-140">С помощью атрибута `x:Class` разметка связывается с классом в коде программной части.</span><span class="sxs-lookup"><span data-stu-id="e38a3-140">The `x:Class` attribute is used to associate the markup with the code-behind class.</span></span> <span data-ttu-id="e38a3-141">Метод `InitializeComponent` вызывается из конструктора класса кода программной части для слияния пользовательского интерфейса, определенного в разметке, с классом кода программной части.</span><span class="sxs-lookup"><span data-stu-id="e38a3-141">`InitializeComponent` is called from the code-behind class's constructor to merge the UI that is defined in markup with the code-behind class.</span></span> <span data-ttu-id="e38a3-142">(создается `InitializeComponent` автоматически при построении приложения, поэтому его не нужно реализовывать вручную.) Сочетание `x:Class` и `InitializeComponent` гарантирует, что ваша реализация будет правильно инициализирована при создании.</span><span class="sxs-lookup"><span data-stu-id="e38a3-142">(`InitializeComponent` is generated for you when your application is built, which is why you don't need to implement it manually.) The combination of `x:Class` and `InitializeComponent` ensure that your implementation is correctly initialized whenever it is created.</span></span> <span data-ttu-id="e38a3-143">Класс кода программной части также реализует обработчик событий <xref:System.Windows.Controls.Primitives.ButtonBase.Click> кнопки.</span><span class="sxs-lookup"><span data-stu-id="e38a3-143">The code-behind class also implements an event handler for the button's <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event.</span></span> <span data-ttu-id="e38a3-144">При нажатии на кнопку обработчик событий выводит окно сообщения, вызывая метод <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-144">When the button is clicked, the event handler shows a message box by calling the <xref:System.Windows.MessageBox.Show%2A?displayProperty=fullName> method.</span></span>

<span data-ttu-id="e38a3-145">На следующем рисунке показан результат нажатия кнопки:</span><span class="sxs-lookup"><span data-stu-id="e38a3-145">The following figure shows the result when the button is clicked:</span></span>

![MessageBox](media/introduction-to-wpf/wpfintrofigure25.png)

## <a name="controls"></a><span data-ttu-id="e38a3-147">Элементы управления</span><span class="sxs-lookup"><span data-stu-id="e38a3-147">Controls</span></span>

<span data-ttu-id="e38a3-148">Возможности взаимодействия с пользователем, обеспечиваемые моделью приложения, реализуются с помощью сконструированных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e38a3-148">The user experiences that are delivered by the application model are constructed controls.</span></span> <span data-ttu-id="e38a3-149">В WPF *элемент управления* — это общий термин, который относится к категории классов WPF, размещаемых в окне или на странице, имеющих пользовательский интерфейс и реализующих некоторое поведение.</span><span class="sxs-lookup"><span data-stu-id="e38a3-149">In WPF, *control* is an umbrella term that applies to a category of WPF classes that are hosted in either a window or a page, have a user interface, and implement some behavior.</span></span>

<span data-ttu-id="e38a3-150">Дополнительные сведения см. в разделе [элементы управления](controls/index.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-150">For more information, see [Controls](controls/index.md).</span></span>

### <a name="wpf-controls-by-function"></a><span data-ttu-id="e38a3-151">Функциональная классификация элементов управления WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-151">WPF controls by function</span></span>

<span data-ttu-id="e38a3-152">Ниже перечислены встроенные элементы управления WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-152">The built-in WPF controls are listed here:</span></span>

- <span data-ttu-id="e38a3-153">**Кнопки**: <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.Primitives.RepeatButton> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-153">**Buttons**: <xref:System.Windows.Controls.Button> and <xref:System.Windows.Controls.Primitives.RepeatButton>.</span></span>

- <span data-ttu-id="e38a3-154">**Отображение данных**: <xref:System.Windows.Controls.DataGrid> , <xref:System.Windows.Controls.ListView> и <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-154">**Data Display**: <xref:System.Windows.Controls.DataGrid>, <xref:System.Windows.Controls.ListView>, and <xref:System.Windows.Controls.TreeView>.</span></span>

- <span data-ttu-id="e38a3-155">**Отображение и выбор даты**: <xref:System.Windows.Controls.Calendar> и <xref:System.Windows.Controls.DatePicker> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-155">**Date Display and Selection**: <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>.</span></span>

- <span data-ttu-id="e38a3-156">**Диалоговые окна**: <xref:Microsoft.Win32.OpenFileDialog> , <xref:System.Windows.Controls.PrintDialog> и <xref:Microsoft.Win32.SaveFileDialog> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-156">**Dialog Boxes**: <xref:Microsoft.Win32.OpenFileDialog>, <xref:System.Windows.Controls.PrintDialog>, and <xref:Microsoft.Win32.SaveFileDialog>.</span></span>

- <span data-ttu-id="e38a3-157">**Цифровой рукописный ввод**: <xref:System.Windows.Controls.InkCanvas> и <xref:System.Windows.Controls.InkPresenter> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-157">**Digital Ink**: <xref:System.Windows.Controls.InkCanvas> and <xref:System.Windows.Controls.InkPresenter>.</span></span>

- <span data-ttu-id="e38a3-158">**Документы**: <xref:System.Windows.Controls.DocumentViewer> , <xref:System.Windows.Controls.FlowDocumentPageViewer> , <xref:System.Windows.Controls.FlowDocumentReader> , <xref:System.Windows.Controls.FlowDocumentScrollViewer> и <xref:System.Windows.Controls.StickyNoteControl> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-158">**Documents**: <xref:System.Windows.Controls.DocumentViewer>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentScrollViewer>, and <xref:System.Windows.Controls.StickyNoteControl>.</span></span>

- <span data-ttu-id="e38a3-159">**Входные данные**: <xref:System.Windows.Controls.TextBox> , <xref:System.Windows.Controls.RichTextBox> и <xref:System.Windows.Controls.PasswordBox> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-159">**Input**: <xref:System.Windows.Controls.TextBox>, <xref:System.Windows.Controls.RichTextBox>, and <xref:System.Windows.Controls.PasswordBox>.</span></span>

- <span data-ttu-id="e38a3-160">**Макет**: <xref:System.Windows.Controls.Border> , <xref:System.Windows.Controls.Primitives.BulletDecorator> , <xref:System.Windows.Controls.Canvas> , <xref:System.Windows.Controls.DockPanel> , <xref:System.Windows.Controls.Expander> , <xref:System.Windows.Controls.Grid> , <xref:System.Windows.Controls.GridView> , <xref:System.Windows.Controls.GridSplitter> , <xref:System.Windows.Controls.GroupBox> , <xref:System.Windows.Controls.Panel> , <xref:System.Windows.Controls.Primitives.ResizeGrip> , <xref:System.Windows.Controls.Separator> , <xref:System.Windows.Controls.Primitives.ScrollBar> , <xref:System.Windows.Controls.ScrollViewer> , <xref:System.Windows.Controls.StackPanel> , <xref:System.Windows.Controls.Primitives.Thumb> , <xref:System.Windows.Controls.Viewbox> , <xref:System.Windows.Controls.VirtualizingStackPanel> , <xref:System.Windows.Window> и <xref:System.Windows.Controls.WrapPanel> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-160">**Layout**: <xref:System.Windows.Controls.Border>, <xref:System.Windows.Controls.Primitives.BulletDecorator>, <xref:System.Windows.Controls.Canvas>, <xref:System.Windows.Controls.DockPanel>, <xref:System.Windows.Controls.Expander>, <xref:System.Windows.Controls.Grid>, <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridSplitter>, <xref:System.Windows.Controls.GroupBox>, <xref:System.Windows.Controls.Panel>, <xref:System.Windows.Controls.Primitives.ResizeGrip>, <xref:System.Windows.Controls.Separator>, <xref:System.Windows.Controls.Primitives.ScrollBar>, <xref:System.Windows.Controls.ScrollViewer>, <xref:System.Windows.Controls.StackPanel>, <xref:System.Windows.Controls.Primitives.Thumb>, <xref:System.Windows.Controls.Viewbox>, <xref:System.Windows.Controls.VirtualizingStackPanel>, <xref:System.Windows.Window>, and <xref:System.Windows.Controls.WrapPanel>.</span></span>

- <span data-ttu-id="e38a3-161">**Носитель**: <xref:System.Windows.Controls.Image> , <xref:System.Windows.Controls.MediaElement> и <xref:System.Windows.Controls.SoundPlayerAction> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-161">**Media**: <xref:System.Windows.Controls.Image>, <xref:System.Windows.Controls.MediaElement>, and <xref:System.Windows.Controls.SoundPlayerAction>.</span></span>

- <span data-ttu-id="e38a3-162">**Меню**: <xref:System.Windows.Controls.ContextMenu> , <xref:System.Windows.Controls.Menu> и <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-162">**Menus**: <xref:System.Windows.Controls.ContextMenu>, <xref:System.Windows.Controls.Menu>, and <xref:System.Windows.Controls.ToolBar>.</span></span>

- <span data-ttu-id="e38a3-163">**Навигация**: <xref:System.Windows.Controls.Frame> , <xref:System.Windows.Documents.Hyperlink> , <xref:System.Windows.Controls.Page> , <xref:System.Windows.Navigation.NavigationWindow> и <xref:System.Windows.Controls.TabControl> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-163">**Navigation**: <xref:System.Windows.Controls.Frame>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Controls.Page>, <xref:System.Windows.Navigation.NavigationWindow>, and <xref:System.Windows.Controls.TabControl>.</span></span>

- <span data-ttu-id="e38a3-164">**Выбор**: <xref:System.Windows.Controls.CheckBox> , <xref:System.Windows.Controls.ComboBox> , <xref:System.Windows.Controls.ListBox> , <xref:System.Windows.Controls.RadioButton> и <xref:System.Windows.Controls.Slider> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-164">**Selection**: <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.ComboBox>, <xref:System.Windows.Controls.ListBox>, <xref:System.Windows.Controls.RadioButton>, and <xref:System.Windows.Controls.Slider>.</span></span>

- <span data-ttu-id="e38a3-165">**Сведения о пользователе**: <xref:System.Windows.Controls.AccessText> , <xref:System.Windows.Controls.Label> , <xref:System.Windows.Controls.Primitives.Popup> ,,, и <xref:System.Windows.Controls.ProgressBar> <xref:System.Windows.Controls.Primitives.StatusBar> <xref:System.Windows.Controls.TextBlock> <xref:System.Windows.Controls.ToolTip> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-165">**User Information**: <xref:System.Windows.Controls.AccessText>, <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Primitives.Popup>, <xref:System.Windows.Controls.ProgressBar>, <xref:System.Windows.Controls.Primitives.StatusBar>, <xref:System.Windows.Controls.TextBlock>, and <xref:System.Windows.Controls.ToolTip>.</span></span>

## <a name="input-and-commands"></a><span data-ttu-id="e38a3-166">Ввод данных и команды</span><span class="sxs-lookup"><span data-stu-id="e38a3-166">Input and commands</span></span>

<span data-ttu-id="e38a3-167">Элементы управления чаще всего используются для определения ввода данных пользователем и реагирования на него.</span><span class="sxs-lookup"><span data-stu-id="e38a3-167">Controls most often detect and respond to user input.</span></span> <span data-ttu-id="e38a3-168">[Система ввода WPF](advanced/input-overview.md) использует как прямые, так и перенаправленные события для поддержки ввода текста, управления фокусом и определения положения указателя мыши.</span><span class="sxs-lookup"><span data-stu-id="e38a3-168">The [WPF input system](advanced/input-overview.md) uses both direct and routed events to support text input, focus management, and mouse positioning.</span></span>

<span data-ttu-id="e38a3-169">Приложения часто предъявляют сложные требования к вводу.</span><span class="sxs-lookup"><span data-stu-id="e38a3-169">Applications often have complex input requirements.</span></span> <span data-ttu-id="e38a3-170">WPF предоставляет [систему команд](advanced/commanding-overview.md), которая отделяет действия по вводу данных пользователем от кода, реагирующего на эти действия.</span><span class="sxs-lookup"><span data-stu-id="e38a3-170">WPF provides a [command system](advanced/commanding-overview.md) that separates user-input actions from the code that responds to those actions.</span></span>

## <a name="layout"></a><span data-ttu-id="e38a3-171">Layout</span><span class="sxs-lookup"><span data-stu-id="e38a3-171">Layout</span></span>

<span data-ttu-id="e38a3-172">При создании пользовательского интерфейса вы компонуете элементы управления, настраивая их расположение и размер.</span><span class="sxs-lookup"><span data-stu-id="e38a3-172">When you create a user interface, you arrange your controls by location and size to form a layout.</span></span> <span data-ttu-id="e38a3-173">Основным требованием любого макета является адаптация к изменениям размеров окна и параметров экрана.</span><span class="sxs-lookup"><span data-stu-id="e38a3-173">A key requirement of any layout is to adapt to changes in window size and display settings.</span></span> <span data-ttu-id="e38a3-174">Платформа WPF избавляет вас от необходимости писать код для адаптации макета к таким условиям, предоставляя первоклассную расширяемую систему макета.</span><span class="sxs-lookup"><span data-stu-id="e38a3-174">Rather than forcing you to write the code to adapt a layout in these circumstances, WPF provides a first-class, extensible layout system for you.</span></span>

<span data-ttu-id="e38a3-175">Ключевым элементом системы макета является относительное позиционирование, которое упрощает адаптацию к меняющимся характеристикам окна и экрана.</span><span class="sxs-lookup"><span data-stu-id="e38a3-175">The cornerstone of the layout system is relative positioning, which increases the ability to adapt to changing window and display conditions.</span></span> <span data-ttu-id="e38a3-176">Кроме того, система макета управляет взаимодействием между элементами управления для определения макета.</span><span class="sxs-lookup"><span data-stu-id="e38a3-176">In addition, the layout system manages the negotiation between controls to determine the layout.</span></span> <span data-ttu-id="e38a3-177">Взаимодействие протекает в два этапа: сначала элемент управления сообщает родительскому объекту о требуемом расположении и размере, а затем родительский объект сообщает родительскому элементу, какое пространство он может занять.</span><span class="sxs-lookup"><span data-stu-id="e38a3-177">The negotiation is a two-step process: first, a control tells its parent what location and size it requires; second, the parent tells the control what space it can have.</span></span>

<span data-ttu-id="e38a3-178">Система макета доступна дочерним элементам управления посредством базовых классов WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-178">The layout system is exposed to child controls through base WPF classes.</span></span> <span data-ttu-id="e38a3-179">Для стандартных макетов, таких как сетка, наложение и закрепление, в WPF имеется несколько элементов управления макетом.</span><span class="sxs-lookup"><span data-stu-id="e38a3-179">For common layouts such as grids, stacking, and docking, WPF includes several layout controls:</span></span>

- <span data-ttu-id="e38a3-180"><xref:System.Windows.Controls.Canvas>: дочерние элементы управления предоставляют собственный макет.</span><span class="sxs-lookup"><span data-stu-id="e38a3-180"><xref:System.Windows.Controls.Canvas>: Child controls provide their own layout.</span></span>

- <span data-ttu-id="e38a3-181"><xref:System.Windows.Controls.DockPanel>: дочерние элементы управления выравниваются по краям панели.</span><span class="sxs-lookup"><span data-stu-id="e38a3-181"><xref:System.Windows.Controls.DockPanel>: Child controls are aligned to the edges of the panel.</span></span>

- <span data-ttu-id="e38a3-182"><xref:System.Windows.Controls.Grid>: дочерние элементы управления упорядочиваются по строкам и столбцам.</span><span class="sxs-lookup"><span data-stu-id="e38a3-182"><xref:System.Windows.Controls.Grid>: Child controls are positioned by rows and columns.</span></span>

- <span data-ttu-id="e38a3-183"><xref:System.Windows.Controls.StackPanel>: дочерние элементы управления располагаются с наложением по вертикали или по горизонтали.</span><span class="sxs-lookup"><span data-stu-id="e38a3-183"><xref:System.Windows.Controls.StackPanel>: Child controls are stacked either vertically or horizontally.</span></span>

- <span data-ttu-id="e38a3-184"><xref:System.Windows.Controls.VirtualizingStackPanel>: дочерние элементы управления виртуализируются и располагаются в линию по горизонтали или по вертикали.</span><span class="sxs-lookup"><span data-stu-id="e38a3-184"><xref:System.Windows.Controls.VirtualizingStackPanel>: Child controls are virtualized and arranged on a single line that is either horizontally or vertically oriented.</span></span>

- <span data-ttu-id="e38a3-185"><xref:System.Windows.Controls.WrapPanel>: дочерние элементы управления располагаются в порядке слева направо и переносятся на следующую строку, если не помещаются в текущей.</span><span class="sxs-lookup"><span data-stu-id="e38a3-185"><xref:System.Windows.Controls.WrapPanel>: Child controls are positioned in left-to-right order and wrapped to the next line when there are more controls on the current line than space allows.</span></span>

<span data-ttu-id="e38a3-186">В следующем примере <xref:System.Windows.Controls.DockPanel> для размещения нескольких <xref:System.Windows.Controls.TextBox> элементов управления используется.</span><span class="sxs-lookup"><span data-stu-id="e38a3-186">The following example uses a <xref:System.Windows.Controls.DockPanel> to lay out several <xref:System.Windows.Controls.TextBox> controls:</span></span>

[!code-xaml[IntroToWPFSnippets#LayoutMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_1.xaml)]

<span data-ttu-id="e38a3-187">Элемент управления <xref:System.Windows.Controls.DockPanel> позволяет дочерним элементам <xref:System.Windows.Controls.TextBox> сообщать, как они должны быть упорядочены.</span><span class="sxs-lookup"><span data-stu-id="e38a3-187">The <xref:System.Windows.Controls.DockPanel> allows the child <xref:System.Windows.Controls.TextBox> controls to tell it how to arrange them.</span></span> <span data-ttu-id="e38a3-188">Для этого в <xref:System.Windows.Controls.DockPanel> реализовано присоединенное свойство `Dock`, которое доступно дочерним элементам управления и позволяет каждому из них указывать стиль закрепления.</span><span class="sxs-lookup"><span data-stu-id="e38a3-188">To do this, the <xref:System.Windows.Controls.DockPanel> implements a `Dock` attached property that is exposed to the child controls to allow each of them to specify a dock style.</span></span>

> [!NOTE]
> <span data-ttu-id="e38a3-189">Свойство, которое реализуется родительским элементом управления для использования дочерними элементами, представляет собой конструкцию WPF, называемую [присоединенным свойством](advanced/attached-properties-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-189">A property that's implemented by a parent control for use by child controls is a WPF construct called an [attached property](advanced/attached-properties-overview.md).</span></span>

<span data-ttu-id="e38a3-190">На следующем рисунке показан результат разметки XAML в предыдущем примере:</span><span class="sxs-lookup"><span data-stu-id="e38a3-190">The following figure shows the result of the XAML markup in the preceding example:</span></span>

![Страница DockPanel](media/introduction-to-wpf/wpfintrofigure11.png)

## <a name="data-binding"></a><span data-ttu-id="e38a3-192">привязка данных,</span><span class="sxs-lookup"><span data-stu-id="e38a3-192">Data binding</span></span>

<span data-ttu-id="e38a3-193">Большинство приложений предоставляют пользователям возможность просматривать и редактировать данные.</span><span class="sxs-lookup"><span data-stu-id="e38a3-193">Most applications are created to provide users with the means to view and edit data.</span></span> <span data-ttu-id="e38a3-194">Для приложений WPF задачи хранения данных и доступа к ним уже обеспечиваются такими технологиями, как SQL Server и ADO .NET.</span><span class="sxs-lookup"><span data-stu-id="e38a3-194">For WPF applications, the work of storing and accessing data is already provided for by technologies such as SQL Server and ADO .NET.</span></span> <span data-ttu-id="e38a3-195">После получения доступа к данным и их загрузки в управляемые объекты приложения WPF начинается самое сложное.</span><span class="sxs-lookup"><span data-stu-id="e38a3-195">After the data is accessed and loaded into an application's managed objects, the hard work for WPF applications begins.</span></span> <span data-ttu-id="e38a3-196">Фактически этот процесс состоит из двух этапов:</span><span class="sxs-lookup"><span data-stu-id="e38a3-196">Essentially, this involves two things:</span></span>

1. <span data-ttu-id="e38a3-197">копирование данных из управляемых объектов в элементы управления для их отображения и редактирования;</span><span class="sxs-lookup"><span data-stu-id="e38a3-197">Copying the data from the managed objects into controls, where the data can be displayed and edited.</span></span>

2. <span data-ttu-id="e38a3-198">обеспечение копирования изменений, внесенных в данные с помощью элементов управления, обратно в управляемые объекты.</span><span class="sxs-lookup"><span data-stu-id="e38a3-198">Ensuring that changes made to data by using controls are copied back to the managed objects.</span></span>

<span data-ttu-id="e38a3-199">Чтобы упростить разработку приложений, платформа WPF предоставляет механизм привязки данных для автоматического выполнения этих действий.</span><span class="sxs-lookup"><span data-stu-id="e38a3-199">To simplify application development, WPF provides a data binding engine to automatically perform these steps.</span></span> <span data-ttu-id="e38a3-200">Основной элемент механизма привязки данных — класс <xref:System.Windows.Data.Binding> , задачей которого является привязка элемента управления (целевого объекта привязки) к объекту данных (источнику привязки).</span><span class="sxs-lookup"><span data-stu-id="e38a3-200">The core unit of the data binding engine is the <xref:System.Windows.Data.Binding> class, whose job is to bind a control (the binding target) to a data object (the binding source).</span></span> <span data-ttu-id="e38a3-201">Эта связь показана на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="e38a3-201">This relationship is illustrated by the following figure:</span></span>

![Основная схема привязки данных](media/introduction-to-wpf/databindingmostbasic.png)

<span data-ttu-id="e38a3-203">В следующем примере показано, как привязать элемент управления <xref:System.Windows.Controls.TextBox> к экземпляру пользовательского объекта `Person`.</span><span class="sxs-lookup"><span data-stu-id="e38a3-203">The next example demonstrates how to bind a <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object.</span></span> <span data-ttu-id="e38a3-204">Реализация `Person` показана в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="e38a3-204">The `Person` implementation is shown in the following code:</span></span>

[!code-vb[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_2.vb)]
[!code-csharp[SimpleDataBindingSnippets#PersonClassCODE](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_2.cs)]

<span data-ttu-id="e38a3-205">Следующая разметка привязывает объект <xref:System.Windows.Controls.TextBox> к экземпляру пользовательского `Person` объекта:</span><span class="sxs-lookup"><span data-stu-id="e38a3-205">The following markup binds the <xref:System.Windows.Controls.TextBox> to an instance of a custom `Person` object:</span></span>

```xaml
 <Window
     xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
     xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
     x:Class="SDKSample.DataBindingWindow">

   <!-- Bind the TextBox to the data source (TextBox.Text to Person.Name) -->
   <TextBox Name="personNameTextBox" Text="{Binding Path=Name}" />

 </Window>
```

[!code-vb[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_6.vb)]
[!code-csharp[SimpleDataBindingSnippets#DataBindingCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_6.cs)]

<span data-ttu-id="e38a3-206">В этом примере экземпляр класса `Person` создается в коде программной части и устанавливается в качестве контекста данных для `DataBindingWindow`.</span><span class="sxs-lookup"><span data-stu-id="e38a3-206">In this example, the `Person` class is instantiated in code-behind and is set as the data context for the `DataBindingWindow`.</span></span> <span data-ttu-id="e38a3-207">В разметке свойство <xref:System.Windows.Controls.TextBox.Text%2A> элемента управления <xref:System.Windows.Controls.TextBox> привязывается к свойству `Person.Name` (с помощью синтаксической конструкции «`{Binding ... }`» языка XAML).</span><span class="sxs-lookup"><span data-stu-id="e38a3-207">In markup, the <xref:System.Windows.Controls.TextBox.Text%2A> property of the <xref:System.Windows.Controls.TextBox> is bound to the `Person.Name` property (using the "`{Binding ... }`" XAML syntax).</span></span> <span data-ttu-id="e38a3-208">Этот код XAML предписывает платформе WPF привязать элемент управления <xref:System.Windows.Controls.TextBox> к объекту `Person` , который хранится в свойстве <xref:System.Windows.FrameworkElement.DataContext%2A> окна.</span><span class="sxs-lookup"><span data-stu-id="e38a3-208">This XAML tells WPF to bind the <xref:System.Windows.Controls.TextBox> control to the `Person` object that is stored in the <xref:System.Windows.FrameworkElement.DataContext%2A> property of the window.</span></span>

<span data-ttu-id="e38a3-209">Механизм привязки данных WPF поддерживает дополнительные возможности, включая проверку, сортировку, фильтрацию и группировку.</span><span class="sxs-lookup"><span data-stu-id="e38a3-209">The WPF data binding engine provides additional support that includes validation, sorting, filtering, and grouping.</span></span> <span data-ttu-id="e38a3-210">Кроме того, привязка данных поддерживает использование шаблонов данных с целью создания настраиваемого пользовательского интерфейса для связанных данных, если пользовательский интерфейс на основе стандартных элементов управления WPF не удовлетворяет требованиям.</span><span class="sxs-lookup"><span data-stu-id="e38a3-210">Furthermore, data binding supports the use of data templates to create custom user interface for bound data when the user interface displayed by the standard WPF controls is not appropriate.</span></span>

<span data-ttu-id="e38a3-211">Дополнительные сведения см. в разделе [Общие сведения о привязке данных](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-211">For more information, see [Data binding overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

## <a name="graphics"></a><span data-ttu-id="e38a3-212">Графика</span><span class="sxs-lookup"><span data-stu-id="e38a3-212">Graphics</span></span>

<span data-ttu-id="e38a3-213">Платформа WPF предоставляет широкий, гибкий и масштабируемый набор графических функций, который обладает перечисленными ниже преимуществами.</span><span class="sxs-lookup"><span data-stu-id="e38a3-213">WPF introduces an extensive, scalable, and flexible set of graphics features that have the following benefits:</span></span>

- <span data-ttu-id="e38a3-214">**Независимость графики от разрешения и устройства**.</span><span class="sxs-lookup"><span data-stu-id="e38a3-214">**Resolution-independent and device-independent graphics**.</span></span> <span data-ttu-id="e38a3-215">Основной единицей измерения в графической системе WPF является аппаратно-независимый пиксель, размер которого составляет 1/96 дюйма вне зависимости от разрешения экрана. Это создает основу для независимой от разрешения и аппаратной платформы отрисовки.</span><span class="sxs-lookup"><span data-stu-id="e38a3-215">The basic unit of measurement in the WPF graphics system is the device-independent pixel, which is 1/96th of an inch, regardless of actual screen resolution, and provides the foundation for resolution-independent and device-independent rendering.</span></span> <span data-ttu-id="e38a3-216">Каждый аппаратно-независимый пиксель автоматически масштабируется в соответствии с заданным в системе количеством точек на дюйм (DPI).</span><span class="sxs-lookup"><span data-stu-id="e38a3-216">Each device-independent pixel automatically scales to match the dots-per-inch (dpi) setting of the system it renders on.</span></span>

- <span data-ttu-id="e38a3-217">**Повышение точности**.</span><span class="sxs-lookup"><span data-stu-id="e38a3-217">**Improved precision**.</span></span> <span data-ttu-id="e38a3-218">Система координат WPF основана на числах двойной точности с плавающей запятой, а не числах одинарной точности.</span><span class="sxs-lookup"><span data-stu-id="e38a3-218">The WPF coordinate system is measured with double-precision floating-point numbers rather than single-precision.</span></span> <span data-ttu-id="e38a3-219">Значения преобразования и прозрачности также выражаются числами двойной точности.</span><span class="sxs-lookup"><span data-stu-id="e38a3-219">Transformations and opacity values are also expressed as double-precision.</span></span> <span data-ttu-id="e38a3-220">Платформа WPF также поддерживает широкую цветовую палитру (scRGB) и имеет встроенную поддержку управления входными данными из разных цветовых схем.</span><span class="sxs-lookup"><span data-stu-id="e38a3-220">WPF also supports a wide color gamut (scRGB) and provides integrated support for managing inputs from different color spaces.</span></span>

- <span data-ttu-id="e38a3-221">**Расширенная поддержка графики и анимации**.</span><span class="sxs-lookup"><span data-stu-id="e38a3-221">**Advanced graphics and animation support**.</span></span> <span data-ttu-id="e38a3-222">Платформа WPF упрощает программирование графики, автоматически управляя анимированными сценами. Вам не нужно беспокоиться об обработке сцен, циклах отрисовки и билинейной интерполяции.</span><span class="sxs-lookup"><span data-stu-id="e38a3-222">WPF simplifies graphics programming by managing animation scenes for you; there is no need to worry about scene processing, rendering loops, and bilinear interpolation.</span></span> <span data-ttu-id="e38a3-223">Кроме того, WPF обеспечивает поддержку проверки попадания и полную поддержку альфа-версии компоновки.</span><span class="sxs-lookup"><span data-stu-id="e38a3-223">Additionally, WPF provides hit-testing support and full alpha-compositing support.</span></span>

- <span data-ttu-id="e38a3-224">**Аппаратное ускорение**.</span><span class="sxs-lookup"><span data-stu-id="e38a3-224">**Hardware acceleration**.</span></span> <span data-ttu-id="e38a3-225">Система графики WPF использует возможности графического оборудования, чтобы снизить нагрузку на ЦП.</span><span class="sxs-lookup"><span data-stu-id="e38a3-225">The WPF graphics system takes advantage of graphics hardware to minimize CPU usage.</span></span>

### <a name="2d-shapes"></a><span data-ttu-id="e38a3-226">Двумерные фигуры</span><span class="sxs-lookup"><span data-stu-id="e38a3-226">2D shapes</span></span>

<span data-ttu-id="e38a3-227">WPF предоставляет библиотеку стандартных векторных двумерных фигур, таких как прямоугольники и эллипсы, которые показаны на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="e38a3-227">WPF provides a library of common vector-drawn 2D shapes, such as the rectangles and ellipses that are shown in the following illustration:</span></span>

![Эллипсы и прямоугольники](media/introduction-to-wpf/wpfintrofigure4.PNG)

<span data-ttu-id="e38a3-229">Интересной особенностью фигур является то, что они предназначены не только для отображения. В них реализованы многие возможности элементов управления, включая ввод с клавиатуры и с помощью мыши.</span><span class="sxs-lookup"><span data-stu-id="e38a3-229">An interesting capability of shapes is that they are not just for display; shapes implement many of the features that you expect from controls, including keyboard and mouse input.</span></span> <span data-ttu-id="e38a3-230">В следующем примере показано <xref:System.Windows.UIElement.MouseUp> событие <xref:System.Windows.Shapes.Ellipse> обрабатываемого объекта:</span><span class="sxs-lookup"><span data-stu-id="e38a3-230">The following example shows the <xref:System.Windows.UIElement.MouseUp> event of an <xref:System.Windows.Shapes.Ellipse> being handled:</span></span>

[!code-xaml[IntroToWPFSnippets#HandleEllipseMouseUpEventMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_7.xaml)]

[!code-vb[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_8.vb)]
[!code-csharp[IntroToWPFSnippets#HandleEllipseMouseUpEventCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_8.cs)]

<span data-ttu-id="e38a3-231">На следующем рисунке показано, что создается в приведенном выше коде.</span><span class="sxs-lookup"><span data-stu-id="e38a3-231">The following figure shows what is produced by the preceding code:</span></span>

![Окно с текстом "you clicked the ellipse&#33;"](media/introduction-to-wpf/wpfintrofigure12.png)

<span data-ttu-id="e38a3-233">Дополнительные сведения см. [в статье Общие сведения о фигурах и базовом рисовании в WPF](../../desktop-wpf/data/data-binding-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-233">For more information, see [Shapes and basic drawing in WPF overview](../../desktop-wpf/data/data-binding-overview.md).</span></span>

### <a name="2d-geometries"></a><span data-ttu-id="e38a3-234">Двумерные геометрические объекты</span><span class="sxs-lookup"><span data-stu-id="e38a3-234">2D geometries</span></span>

<span data-ttu-id="e38a3-235">Двумерные фигуры, предоставляемые WPF, включают в себя стандартный набор базовых фигур.</span><span class="sxs-lookup"><span data-stu-id="e38a3-235">The 2D shapes provided by WPF cover the standard set of basic shapes.</span></span> <span data-ttu-id="e38a3-236">Однако вам может потребоваться создать собственные фигуры, чтобы упростить разработку пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e38a3-236">However, you may need to create custom shapes to facilitate the design of a customized user interface.</span></span> <span data-ttu-id="e38a3-237">Для этой цели WPF предоставляет геометрические объекты.</span><span class="sxs-lookup"><span data-stu-id="e38a3-237">For this purpose, WPF provides geometries.</span></span> <span data-ttu-id="e38a3-238">На рисунке ниже демонстрируется использование геометрических объектов для создания пользовательской фигуры, которую можно нарисовать напрямую, применять как кисть или использовать для обрезки других фигур и элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e38a3-238">The following figure demonstrates the use of geometries to create a custom shape that can be drawn directly, used as a brush, or used to clip other shapes and controls.</span></span>

<span data-ttu-id="e38a3-239">Объекты<xref:System.Windows.Shapes.Path> можно использовать для рисования замкнутых и незамкнутых фигур, нескольких фигур и даже криволинейных фигур.</span><span class="sxs-lookup"><span data-stu-id="e38a3-239"><xref:System.Windows.Shapes.Path> objects can be used to draw closed or open shapes, multiple shapes, and even curved shapes.</span></span>

<span data-ttu-id="e38a3-240">Объекты <xref:System.Windows.Media.Geometry> можно использовать для обрезки, проверки попадания и отрисовки двумерных графических данных.</span><span class="sxs-lookup"><span data-stu-id="e38a3-240"><xref:System.Windows.Media.Geometry> objects can be used for clipping, hit-testing, and rendering 2D graphic data.</span></span>

![Различные способы использования Path](media/introduction-to-wpf/wpfintrofigure5.png)

<span data-ttu-id="e38a3-242">Дополнительные сведения см. в разделе [Общие сведения о классе Geometry](graphics-multimedia/geometry-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-242">For more information, see [Geometry overview](graphics-multimedia/geometry-overview.md).</span></span>

### <a name="2d-effects"></a><span data-ttu-id="e38a3-243">Двумерные эффекты</span><span class="sxs-lookup"><span data-stu-id="e38a3-243">2D effects</span></span>

<span data-ttu-id="e38a3-244">В число возможностей двумерной графики WPF входят визуальные эффекты, такие как градиенты, растровые изображения, рисунки, рисование с видео, вращение, масштабирование и наклон.</span><span class="sxs-lookup"><span data-stu-id="e38a3-244">A subset of WPF 2D capabilities includes visual effects, such as gradients, bitmaps, drawings, painting with videos, rotation, scaling, and skewing.</span></span> <span data-ttu-id="e38a3-245">Все это достигается с помощью кистей; на следующем рисунке показаны некоторые примеры.</span><span class="sxs-lookup"><span data-stu-id="e38a3-245">These are all achieved with brushes; the following figure shows some examples:</span></span>

![Иллюстрация различных кистей](media/introduction-to-wpf/wpfintrofigure6.png)

<span data-ttu-id="e38a3-247">Дополнительные сведения см. в разделе [Общие сведения о кистях WPF](graphics-multimedia/wpf-brushes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-247">For more information, see [WPF brushes overview](graphics-multimedia/wpf-brushes-overview.md).</span></span>

### <a name="3d-rendering"></a><span data-ttu-id="e38a3-248">Трехмерная отрисовка</span><span class="sxs-lookup"><span data-stu-id="e38a3-248">3D rendering</span></span>

<span data-ttu-id="e38a3-249">WPF также включает возможности трехмерной отрисовки, которые интегрируются с двухмерной графикой, что позволяет создавать более интересные и интересные пользовательские интерфейсы.</span><span class="sxs-lookup"><span data-stu-id="e38a3-249">WPF also includes 3D rendering capabilities that integrate with 2D graphics to allow the creation of more exciting and interesting user interfaces.</span></span> <span data-ttu-id="e38a3-250">Например, на следующем рисунке показаны двумерные изображения, отображаемые на трехмерных фигурах:</span><span class="sxs-lookup"><span data-stu-id="e38a3-250">For example, the following figure shows 2D images rendered onto 3D shapes:</span></span>

![Снимок экрана примера Visual3D](media/introduction-to-wpf/wpfintrofigure13.png)

<span data-ttu-id="e38a3-252">Дополнительные сведения см. в статье [Обзор трехмерной графики](graphics-multimedia/3-d-graphics-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-252">For more information, see [3D graphics overview](graphics-multimedia/3-d-graphics-overview.md).</span></span>

## <a name="animation"></a><span data-ttu-id="e38a3-253">Анимация</span><span class="sxs-lookup"><span data-stu-id="e38a3-253">Animation</span></span>

<span data-ttu-id="e38a3-254">Поддержка анимации в WPF позволяет применять к элементам управления такие эффекты, как увеличение, дрожание, вращение и исчезание, создавать интересные эффекты смены страниц и другие эффекты.</span><span class="sxs-lookup"><span data-stu-id="e38a3-254">WPF animation support lets you make controls grow, shake, spin, and fade, to create interesting page transitions, and more.</span></span> <span data-ttu-id="e38a3-255">Вы можете анимировать большинство классов WPF, даже настраиваемые классы.</span><span class="sxs-lookup"><span data-stu-id="e38a3-255">You can animate most WPF classes, even custom classes.</span></span> <span data-ttu-id="e38a3-256">На следующем рисунке показана простая анимация в действии:</span><span class="sxs-lookup"><span data-stu-id="e38a3-256">The following figure shows a simple animation in action:</span></span>

![Изображения анимированного куба](media/introduction-to-wpf/wpfintrofigure7.png)

<span data-ttu-id="e38a3-258">Дополнительные сведения см. в разделе [Общие сведения об эффектах анимации](graphics-multimedia/animation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-258">For more information, see [Animation overview](graphics-multimedia/animation-overview.md).</span></span>

## <a name="media"></a><span data-ttu-id="e38a3-259">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="e38a3-259">Media</span></span>

<span data-ttu-id="e38a3-260">Одни из способов передачи более информативного содержимого — использовать аудиовизуальные средства.</span><span class="sxs-lookup"><span data-stu-id="e38a3-260">One way to convey rich content is through the use of audiovisual media.</span></span> <span data-ttu-id="e38a3-261">WPF обеспечивает специальную поддержку изображений, видео и звука.</span><span class="sxs-lookup"><span data-stu-id="e38a3-261">WPF provides special support for images, video, and audio.</span></span>

### <a name="images"></a><span data-ttu-id="e38a3-262">Изображения</span><span class="sxs-lookup"><span data-stu-id="e38a3-262">Images</span></span>

<span data-ttu-id="e38a3-263">Изображения присутствуют в большинстве приложений, и платформа WPF предоставляет несколько способов их использования.</span><span class="sxs-lookup"><span data-stu-id="e38a3-263">Images are common to most applications, and WPF provides several ways to use them.</span></span> <span data-ttu-id="e38a3-264">На рисунке ниже показан пользовательский интерфейс со списком, содержащим эскизы.</span><span class="sxs-lookup"><span data-stu-id="e38a3-264">The following figure shows a user interface with a list box that contains thumbnail images.</span></span> <span data-ttu-id="e38a3-265">При выборе эскиза изображение отображается в полном размере.</span><span class="sxs-lookup"><span data-stu-id="e38a3-265">When a thumbnail is selected, the image is shown full-size.</span></span>

![Эскизы и полноразмерное изображение](media/introduction-to-wpf/wpfintrofigure8.png)

<span data-ttu-id="e38a3-267">Дополнительные сведения см. в разделе [Общие сведения об обработке изображений](graphics-multimedia/imaging-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-267">For more information, see [Imaging overview](graphics-multimedia/imaging-overview.md).</span></span>

### <a name="video-and-audio"></a><span data-ttu-id="e38a3-268">Видео и звук</span><span class="sxs-lookup"><span data-stu-id="e38a3-268">Video and audio</span></span>

<span data-ttu-id="e38a3-269">Элемент управления <xref:System.Windows.Controls.MediaElement> позволяет воспроизводить как видео, так и звук и достаточно гибок для того, чтобы служить основой для пользовательского мультимедиапроигрывателя.</span><span class="sxs-lookup"><span data-stu-id="e38a3-269">The <xref:System.Windows.Controls.MediaElement> control is capable of playing both video and audio, and it is flexible enough to be the basis for a custom media player.</span></span> <span data-ttu-id="e38a3-270">Следующая разметка XAML реализует проигрыватель мультимедиа:</span><span class="sxs-lookup"><span data-stu-id="e38a3-270">The following XAML markup implements a media player:</span></span>

[!code-xaml[IntroToWPFSnippets#MediaElementMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_9.xaml)]

<span data-ttu-id="e38a3-271">В окне на следующем рисунке показан <xref:System.Windows.Controls.MediaElement> элемент управления в действии:</span><span class="sxs-lookup"><span data-stu-id="e38a3-271">The window in the following figure shows the <xref:System.Windows.Controls.MediaElement> control in action:</span></span>

![Элемент управления MediaElement с аудио и видео](media/introduction-to-wpf/wpfintrofigure1.png)

<span data-ttu-id="e38a3-273">Дополнительные сведения см. в разделе [Графика и мультимедиа](graphics-multimedia/index.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-273">For more information, see [Graphics and multimedia](graphics-multimedia/index.md).</span></span>

## <a name="text-and-typography"></a><span data-ttu-id="e38a3-274">Текст и типографическая разметка</span><span class="sxs-lookup"><span data-stu-id="e38a3-274">Text and typography</span></span>

<span data-ttu-id="e38a3-275">Чтобы упростить высококачественную отрисовку текста, платформа WPF предоставляет следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="e38a3-275">To facilitate high-quality text rendering, WPF offers the following features:</span></span>

- <span data-ttu-id="e38a3-276">поддержка шрифтов OpenType;</span><span class="sxs-lookup"><span data-stu-id="e38a3-276">OpenType font support.</span></span>

- <span data-ttu-id="e38a3-277">усовершенствования ClearType;</span><span class="sxs-lookup"><span data-stu-id="e38a3-277">ClearType enhancements.</span></span>

- <span data-ttu-id="e38a3-278">высокая производительность за счет аппаратного ускорения;</span><span class="sxs-lookup"><span data-stu-id="e38a3-278">High performance that takes advantage of hardware acceleration.</span></span>

- <span data-ttu-id="e38a3-279">интеграция текста с мультимедиа, графикой и анимацией;</span><span class="sxs-lookup"><span data-stu-id="e38a3-279">Integration of text with media, graphics, and animation.</span></span>

- <span data-ttu-id="e38a3-280">поддержка международных шрифтов и резервных механизмов.</span><span class="sxs-lookup"><span data-stu-id="e38a3-280">International font support and fallback mechanisms.</span></span>

<span data-ttu-id="e38a3-281">В качестве демонстрации интеграции текста с графикой на следующем рисунке показано применение украшений текста.</span><span class="sxs-lookup"><span data-stu-id="e38a3-281">As a demonstration of text integration with graphics, the following figure shows the application of text decorations:</span></span>

![Текст с различными украшениями](media/introduction-to-wpf/wpfintrofigure23.png)

<span data-ttu-id="e38a3-283">Более подробную информацию см. в разделе [Типографическая разметка в Windows Presentation Foundation](advanced/typography-in-wpf.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-283">For more information, see [Typography in Windows Presentation Foundation](advanced/typography-in-wpf.md).</span></span>

## <a name="customize-wpf-apps"></a><span data-ttu-id="e38a3-284">Настройка приложений WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-284">Customize WPF apps</span></span>

<span data-ttu-id="e38a3-285">До сих пор мы рассматривали основные строительные блоки WPF для разработки приложений.</span><span class="sxs-lookup"><span data-stu-id="e38a3-285">Up to this point, you've seen the core WPF building blocks for developing applications.</span></span> <span data-ttu-id="e38a3-286">Для размещения и предоставления содержимого приложения, состоящего в основном из элементов управления, используется модель приложения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-286">You use the application model to host and deliver application content, which consists mainly of controls.</span></span> <span data-ttu-id="e38a3-287">Для упрощения размещения элементов управления в пользовательском интерфейсе и сохранения их компоновки в случае изменения размера окна или параметров экрана используется система макета WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-287">To simplify the arrangement of controls in a user interface, and to ensure the arrangement is maintained in the face of changes to window size and display settings, you use the WPF layout system.</span></span> <span data-ttu-id="e38a3-288">Так как большинство приложений предоставляют пользователям возможность взаимодействовать с данными, для сокращения объема работы, необходимой для интеграции пользовательского интерфейса с данными, используется привязка данных.</span><span class="sxs-lookup"><span data-stu-id="e38a3-288">Because most applications let users interact with data, you use data binding to reduce the work of integrating your user interface with data.</span></span> <span data-ttu-id="e38a3-289">Чтобы улучшить внешний вид приложения, используется широкий ряд средств графики, анимации и мультимедиа, предоставляемый платформой WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-289">To enhance the visual appearance of your application, you use the comprehensive range of graphics, animation, and media support provided by WPF.</span></span>

<span data-ttu-id="e38a3-290">Однако зачастую этих основных средств недостаточно для создания уникального и визуально привлекательного пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="e38a3-290">Often, though, the basics are not enough for creating and managing a truly distinct and visually stunning user experience.</span></span> <span data-ttu-id="e38a3-291">Стандартные элементы управления WPF могут не сочетаться с требуемым оформлением вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-291">The standard WPF controls might not integrate with the desired appearance of your application.</span></span> <span data-ttu-id="e38a3-292">Данные могут отображаться не самым эффективным образом.</span><span class="sxs-lookup"><span data-stu-id="e38a3-292">Data might not be displayed in the most effective way.</span></span> <span data-ttu-id="e38a3-293">Пользовательскому интерфейсу вашего приложения может в целом не подходить внешний вид тем Windows по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e38a3-293">Your application's overall user experience may not be suited to the default look and feel of Windows themes.</span></span> <span data-ttu-id="e38a3-294">Наряду с другими типами расширяемости, технологии представления во многих случаях требуется визуальная расширяемость.</span><span class="sxs-lookup"><span data-stu-id="e38a3-294">In many ways, a presentation technology needs visual extensibility as much as any other type of extensibility.</span></span>

<span data-ttu-id="e38a3-295">По этой причине WPF предоставляет разнообразные механизмы создания уникальных пользовательских интерфейсов, включая модель мультимедийного содержимого для элементов управления, триггеры, шаблоны элементов управления и данных, стили, ресурсы пользовательского интерфейса, темы и обложки.</span><span class="sxs-lookup"><span data-stu-id="e38a3-295">For this reason, WPF provides a variety of mechanisms for creating unique user experiences, including a rich content model for controls, triggers, control and data templates, styles, user interface resources, and themes and skins.</span></span>

### <a name="content-model"></a><span data-ttu-id="e38a3-296">Модель содержимого</span><span class="sxs-lookup"><span data-stu-id="e38a3-296">Content model</span></span>

<span data-ttu-id="e38a3-297">Основным назначением большинства элементов управления WPF является отображение содержимого.</span><span class="sxs-lookup"><span data-stu-id="e38a3-297">The main purpose of a majority of the WPF controls is to display content.</span></span> <span data-ttu-id="e38a3-298">В WPF тип и число элементов, составляющих содержимое элемента управления, называются *моделью содержимого*элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e38a3-298">In WPF, the type and number of items that can constitute the content of a control is referred to as the control's *content model*.</span></span> <span data-ttu-id="e38a3-299">Некоторые элементы могут содержать только один объект и только один тип содержимого. Например, содержимым элемента управления <xref:System.Windows.Controls.TextBox> является строковое значение, присвоенное свойству <xref:System.Windows.Controls.TextBox.Text%2A> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-299">Some controls can contain a single item and type of content; for example, the content of a <xref:System.Windows.Controls.TextBox> is a string value that is assigned to the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span> <span data-ttu-id="e38a3-300">В следующем примере задается содержимое <xref:System.Windows.Controls.TextBox> :</span><span class="sxs-lookup"><span data-stu-id="e38a3-300">The following example sets the content of a <xref:System.Windows.Controls.TextBox>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.TextBoxContentWindow"
    Title="TextBox Content">

    <TextBox Text="This is the content of a TextBox." />
</Window>
```

<span data-ttu-id="e38a3-301">На следующем рисунке показан результат.</span><span class="sxs-lookup"><span data-stu-id="e38a3-301">The following figure shows the result:</span></span>

![Элемент управления TextBox с текстом](media/introduction-to-wpf/wpfintrofigure21.png)

<span data-ttu-id="e38a3-303">Другие элементы управления, однако, могут содержать несколько объектов с различным типом содержимого. Содержимым элемента управления <xref:System.Windows.Controls.Button>, определяемым свойством <xref:System.Windows.Controls.ContentControl.Content%2A>, могут быть различные объекты, в том числе элементы управления макетом, текст, изображения и фигуры.</span><span class="sxs-lookup"><span data-stu-id="e38a3-303">Other controls, however, can contain multiple items of different types of content; the content of a <xref:System.Windows.Controls.Button>, specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property, can contain a variety of items including layout controls, text, images, and shapes.</span></span> <span data-ttu-id="e38a3-304">В следующем примере показано <xref:System.Windows.Controls.Button> содержимое с содержимым, включающим,,, <xref:System.Windows.Controls.DockPanel> <xref:System.Windows.Controls.Label> <xref:System.Windows.Controls.Border> и <xref:System.Windows.Controls.MediaElement> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-304">The following example shows a <xref:System.Windows.Controls.Button> with content that includes a <xref:System.Windows.Controls.DockPanel>, a <xref:System.Windows.Controls.Label>, a <xref:System.Windows.Controls.Border>, and a <xref:System.Windows.Controls.MediaElement>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ButtonContentWindow"
    Title="Button Content">

  <Button Margin="20">
    <!-- Button Content -->
    <DockPanel Width="200" Height="180">
      <Label DockPanel.Dock="Top" HorizontalAlignment="Center">Click Me!</Label>
      <Border Background="Black" BorderBrush="Yellow" BorderThickness="2"
        CornerRadius="2" Margin="5">
        <MediaElement Source="media/wpf.wmv" Stretch="Fill" />
      </Border>
    </DockPanel>
  </Button>
</Window>
```

<span data-ttu-id="e38a3-305">На следующем рисунке показано содержимое этой кнопки:</span><span class="sxs-lookup"><span data-stu-id="e38a3-305">The following figure shows the content of this button:</span></span>

![Кнопка с множественными типами содержания](media/introduction-to-wpf/wpfintrofigure22.png)

<span data-ttu-id="e38a3-307">Дополнительную информацию о типах содержимого, поддерживаемого различными элементами управления, см. в разделе [Модель содержимого WPF](controls/wpf-content-model.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-307">For more information on the kinds of content that is supported by various controls, see [WPF content model](controls/wpf-content-model.md).</span></span>

### <a name="triggers"></a><span data-ttu-id="e38a3-308">Триггеры</span><span class="sxs-lookup"><span data-stu-id="e38a3-308">Triggers</span></span>

<span data-ttu-id="e38a3-309">Хотя основным назначением разметки XAML является определение внешнего вида приложения, ее также можно использовать для реализации некоторых аспектов поведения приложения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-309">Although the main purpose of XAML markup is to implement an application's appearance, you can also use XAML to implement some aspects of an application's behavior.</span></span> <span data-ttu-id="e38a3-310">Один из примеров — изменение внешнего вида приложения с помощью триггеров при выполнении пользователем определенных действий.</span><span class="sxs-lookup"><span data-stu-id="e38a3-310">One example is the use of triggers to change an application's appearance based on user interactions.</span></span> <span data-ttu-id="e38a3-311">Дополнительные сведения см. в разделе [Стили и шаблоны](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-311">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="control-templates"></a><span data-ttu-id="e38a3-312">Шаблоны элементов управления</span><span class="sxs-lookup"><span data-stu-id="e38a3-312">Control templates</span></span>

<span data-ttu-id="e38a3-313">Пользовательские интерфейсы по умолчанию для элементов управления WPF обычно формируются на основе других элементов управления и фигур.</span><span class="sxs-lookup"><span data-stu-id="e38a3-313">The default user interfaces for WPF controls are typically constructed from other controls and shapes.</span></span> <span data-ttu-id="e38a3-314">Например, элемент управления <xref:System.Windows.Controls.Button> состоит из элементов управления <xref:Microsoft.Windows.Themes.ButtonChrome> и <xref:System.Windows.Controls.ContentPresenter> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-314">For example, a <xref:System.Windows.Controls.Button> is composed of both <xref:Microsoft.Windows.Themes.ButtonChrome> and <xref:System.Windows.Controls.ContentPresenter> controls.</span></span> <span data-ttu-id="e38a3-315"><xref:Microsoft.Windows.Themes.ButtonChrome> обеспечивает стандартный внешний вид кнопки, а <xref:System.Windows.Controls.ContentPresenter> служит для вывода ее содержимого, определяемого свойством <xref:System.Windows.Controls.ContentControl.Content%2A> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-315">The <xref:Microsoft.Windows.Themes.ButtonChrome> provides the standard button appearance, while the <xref:System.Windows.Controls.ContentPresenter> displays the button's content, as specified by the <xref:System.Windows.Controls.ContentControl.Content%2A> property.</span></span>

<span data-ttu-id="e38a3-316">Иногда внешний вид элемента управления по умолчанию может не согласовываться с общим оформлением приложения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-316">Sometimes the default appearance of a control may be incongruent with the overall appearance of an application.</span></span> <span data-ttu-id="e38a3-317">В этом случае можно использовать <xref:System.Windows.Controls.ControlTemplate> для изменения пользовательского интерфейса элемента управления, не меняя его содержимое и поведение.</span><span class="sxs-lookup"><span data-stu-id="e38a3-317">In this case, you can use a <xref:System.Windows.Controls.ControlTemplate> to change the appearance of the control's user interface without changing its content and behavior.</span></span>

<span data-ttu-id="e38a3-318">В следующем примере показано, как изменить внешний вид с <xref:System.Windows.Controls.Button> помощью <xref:System.Windows.Controls.ControlTemplate> :</span><span class="sxs-lookup"><span data-stu-id="e38a3-318">The following example shows how to change the appearance of a <xref:System.Windows.Controls.Button> by using a <xref:System.Windows.Controls.ControlTemplate>:</span></span>

[!code-xaml[IntroToWPFSnippets#ButtonControlTemplateWindowMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_16.xaml)]

[!code-csharp[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_17.cs)]
[!code-vb[IntroToWPFSnippets#ButtonControlTemplateWindowCODEBEHIND](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_17.vb)]

<span data-ttu-id="e38a3-319">В этом примере пользовательский интерфейс кнопки по умолчанию заменяется элементом <xref:System.Windows.Shapes.Ellipse>, имеющим темно-синюю границу и заполнение, определяемое <xref:System.Windows.Media.RadialGradientBrush>.</span><span class="sxs-lookup"><span data-stu-id="e38a3-319">In this example, the default button user interface has been replaced with an <xref:System.Windows.Shapes.Ellipse> that has a dark blue border and is filled using a <xref:System.Windows.Media.RadialGradientBrush>.</span></span> <span data-ttu-id="e38a3-320">В элементе управления <xref:System.Windows.Controls.ContentPresenter> выводится содержимое элемента <xref:System.Windows.Controls.Button>— текст «Click Me!»</span><span class="sxs-lookup"><span data-stu-id="e38a3-320">The <xref:System.Windows.Controls.ContentPresenter> control displays the content of the <xref:System.Windows.Controls.Button>, "Click Me!"</span></span> <span data-ttu-id="e38a3-321">При нажатии на элемент <xref:System.Windows.Controls.Button> по-прежнему вызывается событие <xref:System.Windows.Controls.Primitives.ButtonBase.Click> , что соответствует поведению элемента управления <xref:System.Windows.Controls.Button> по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e38a3-321">When the <xref:System.Windows.Controls.Button> is clicked, the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event is still raised as part of the <xref:System.Windows.Controls.Button> control's default behavior.</span></span> <span data-ttu-id="e38a3-322">Результат показан на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="e38a3-322">The result is shown in the following figure:</span></span>

![Кнопка в виде эллипса и второе окно](media/introduction-to-wpf/wpfintrofigure2.png)

### <a name="data-templates"></a><span data-ttu-id="e38a3-324">Шаблоны данных</span><span class="sxs-lookup"><span data-stu-id="e38a3-324">Data templates</span></span>

<span data-ttu-id="e38a3-325">В то время как шаблон элемента управления позволяет определять внешний вид элемента управления, шаблон данных дает возможность настраивать оформление его содержимого.</span><span class="sxs-lookup"><span data-stu-id="e38a3-325">Whereas a control template lets you specify the appearance of a control, a data template lets you specify the appearance of a control's content.</span></span> <span data-ttu-id="e38a3-326">Шаблоны данных часто используются для оптимизации отображения привязанных данных.</span><span class="sxs-lookup"><span data-stu-id="e38a3-326">Data templates are frequently used to enhance how bound data is displayed.</span></span> <span data-ttu-id="e38a3-327">На следующем рисунке показан внешний вид по умолчанию для объекта, <xref:System.Windows.Controls.ListBox> привязанного к коллекции `Task` объектов, у каждой задачи есть имя, описание и приоритет:</span><span class="sxs-lookup"><span data-stu-id="e38a3-327">The following figure shows the default appearance for a <xref:System.Windows.Controls.ListBox> that is bound to a collection of `Task` objects, where each task has a name, description, and priority:</span></span>

![Список с видом по умолчанию](media/introduction-to-wpf/wpfintrofigure18.png)

<span data-ttu-id="e38a3-329">Оформление по умолчанию является стандартным для элемента управления <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="e38a3-329">The default appearance is what you would expect from a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="e38a3-330">Однако оно предполагает, что для каждой задачи отображается только ее название.</span><span class="sxs-lookup"><span data-stu-id="e38a3-330">However, the default appearance of each task contains only the task name.</span></span> <span data-ttu-id="e38a3-331">Чтобы отобразить название, описание и приоритет задачи, нужно изменить оформление по умолчанию для элементов списка, привязанных к элементу управления <xref:System.Windows.Controls.ListBox> , с помощью <xref:System.Windows.DataTemplate>.</span><span class="sxs-lookup"><span data-stu-id="e38a3-331">To show the task name, description, and priority, the default appearance of the <xref:System.Windows.Controls.ListBox> control's bound list items must be changed by using a <xref:System.Windows.DataTemplate>.</span></span> <span data-ttu-id="e38a3-332">Следующий код XAML определяет такие <xref:System.Windows.DataTemplate> , которые применяются к каждой задаче с помощью <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> атрибута:</span><span class="sxs-lookup"><span data-stu-id="e38a3-332">The following XAML defines such a <xref:System.Windows.DataTemplate>, which is applied to each task by using the <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> attribute:</span></span>

```xaml
<Window
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
  x:Class="SDKSample.DataTemplateWindow"
  Title="With a Data Template">
  <Window.Resources>
    <!-- Data Template (applied to each bound task item in the task collection) -->
    <DataTemplate x:Key="myTaskTemplate">
      <Border Name="border" BorderBrush="DarkSlateBlue" BorderThickness="2"
        CornerRadius="2" Padding="5" Margin="5">
        <Grid>
          <Grid.RowDefinitions>
            <RowDefinition/>
            <RowDefinition/>
            <RowDefinition/>
          </Grid.RowDefinitions>
          <Grid.ColumnDefinitions>
            <ColumnDefinition Width="Auto" />
            <ColumnDefinition />
          </Grid.ColumnDefinitions>
          <TextBlock Grid.Row="0" Grid.Column="0" Padding="0,0,5,0" Text="Task Name:"/>
          <TextBlock Grid.Row="0" Grid.Column="1" Text="{Binding Path=TaskName}"/>
          <TextBlock Grid.Row="1" Grid.Column="0" Padding="0,0,5,0" Text="Description:"/>
          <TextBlock Grid.Row="1" Grid.Column="1" Text="{Binding Path=Description}"/>
          <TextBlock Grid.Row="2" Grid.Column="0" Padding="0,0,5,0" Text="Priority:"/>
          <TextBlock Grid.Row="2" Grid.Column="1" Text="{Binding Path=Priority}"/>
        </Grid>
      </Border>
    </DataTemplate>
  </Window.Resources>

  <!-- UI -->
  <DockPanel>
    <!-- Title -->
    <Label DockPanel.Dock="Top" FontSize="18" Margin="5" Content="My Task List:"/>

    <!-- Data template is specified by the ItemTemplate attribute -->
    <ListBox
      ItemsSource="{Binding}"
      ItemTemplate="{StaticResource myTaskTemplate}"
      HorizontalContentAlignment="Stretch"
      IsSynchronizedWithCurrentItem="True"
      Margin="5,0,5,5" />

 </DockPanel>
</Window>
```

<span data-ttu-id="e38a3-333">На следующем рисунке показан результат выполнения этого кода:</span><span class="sxs-lookup"><span data-stu-id="e38a3-333">The following figure shows the effect of this code:</span></span>

![Список, использующий шаблон данных](media/introduction-to-wpf/wpfintrofigure19.png)

<span data-ttu-id="e38a3-335">Обратите внимание на то, что элемент управления <xref:System.Windows.Controls.ListBox> сохранил свое поведение и общий внешний вид. Изменилось только оформление содержимого, отображаемого в списке.</span><span class="sxs-lookup"><span data-stu-id="e38a3-335">Note that the <xref:System.Windows.Controls.ListBox> has retained its behavior and overall appearance; only the appearance of the content being displayed by the list box has changed.</span></span>

<span data-ttu-id="e38a3-336">Дополнительные сведения см. в разделе [Общие сведения о шаблонах данных](data/data-templating-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-336">For more information, see [Data templating overview](data/data-templating-overview.md).</span></span>

### <a name="styles"></a><span data-ttu-id="e38a3-337">Стили</span><span class="sxs-lookup"><span data-stu-id="e38a3-337">Styles</span></span>

<span data-ttu-id="e38a3-338">Стили позволяют разработчикам и дизайнерам стандартизировать внешний вид своего продукта.</span><span class="sxs-lookup"><span data-stu-id="e38a3-338">Styles enable developers and designers to standardize on a particular appearance for their product.</span></span> <span data-ttu-id="e38a3-339">Платформа WPF предоставляет строгую модель стилей, в основе которой лежит элемент <xref:System.Windows.Style> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-339">WPF provides a strong style model, the foundation of which is the <xref:System.Windows.Style> element.</span></span> <span data-ttu-id="e38a3-340">В следующем примере создается стиль, который задает для каждого окна цвет фона для каждого <xref:System.Windows.Controls.Button> из окон `Orange` :</span><span class="sxs-lookup"><span data-stu-id="e38a3-340">The following example creates a style that sets the background color for every <xref:System.Windows.Controls.Button> on a window to `Orange`:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.StyleWindow"
    Title="Styles">
  <!-- Style that will be applied to all buttons -->
  <Style TargetType="{x:Type Button}">
    <Setter Property="Background" Value="Orange" />
    <Setter Property="BorderBrush" Value="Crimson" />
    <Setter Property="FontSize" Value="20" />
    <Setter Property="FontWeight" Value="Bold" />
    <Setter Property="Margin" Value="5" />
  </Style>
  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>

  <!-- This label will not have the style applied to it -->
  <Label>Don't Click Me!</Label>

  <!-- This button will have the style applied to it -->
  <Button>Click Me!</Button>
</Window>
```

<span data-ttu-id="e38a3-341">Так как этот стиль предназначен для всех элементов управления <xref:System.Windows.Controls.Button>, он автоматически применяется ко всем кнопкам в окне, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="e38a3-341">Because this style targets all <xref:System.Windows.Controls.Button> controls, the style is automatically applied to all the buttons in the window, as shown in the following figure:</span></span>

![Две оранжевые кнопки](media/introduction-to-wpf/wpfintrofigure20.png)

<span data-ttu-id="e38a3-343">Дополнительные сведения см. в разделе [Стили и шаблоны](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-343">For more information, see [Styles and templates](../../desktop-wpf/fundamentals/styles-templates-overview.md).</span></span>

### <a name="resources"></a><span data-ttu-id="e38a3-344">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="e38a3-344">Resources</span></span>

<span data-ttu-id="e38a3-345">Элементы управления в приложении должны иметь одинаковое оформление, которое может включать любые элементы: от шрифтов и цвета фона до шаблонов элементов управления, шаблонов данных и стилей.</span><span class="sxs-lookup"><span data-stu-id="e38a3-345">Controls in an application should share the same appearance, which can include anything from fonts and background colors to control templates, data templates, and styles.</span></span> <span data-ttu-id="e38a3-346">Благодаря поддержке ресурсов пользовательского интерфейса в WPF можно инкапсулировать эти ресурсы в одном месте для повторного использования.</span><span class="sxs-lookup"><span data-stu-id="e38a3-346">You can use WPF's support for user interface resources to encapsulate these resources in a single location for reuse.</span></span>

<span data-ttu-id="e38a3-347">В следующем примере определяется общий цвет фона, совместно используемый <xref:System.Windows.Controls.Button> и <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="e38a3-347">The following example defines a common background color that is shared by a <xref:System.Windows.Controls.Button> and a <xref:System.Windows.Controls.Label>:</span></span>

```xaml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.ResourcesWindow"
    Title="Resources Window">

  <!-- Define window-scoped background color resource -->
  <Window.Resources>
    <SolidColorBrush x:Key="defaultBackground" Color="Red" />
  </Window.Resources>

  <!-- Button background is defined by window-scoped resource -->
  <Button Background="{StaticResource defaultBackground}">One Button</Button>

  <!-- Label background is defined by window-scoped resource -->
  <Label Background="{StaticResource defaultBackground}">One Label</Label>
</Window>
```

<span data-ttu-id="e38a3-348">Ресурс цвета фона реализуется с помощью элемента свойства `Window.Resources` .</span><span class="sxs-lookup"><span data-stu-id="e38a3-348">This example implements a background color resource by using the `Window.Resources` property element.</span></span> <span data-ttu-id="e38a3-349">Этот ресурс доступен всем дочерним элементам объекта <xref:System.Windows.Window>.</span><span class="sxs-lookup"><span data-stu-id="e38a3-349">This resource is available to all children of the <xref:System.Windows.Window>.</span></span> <span data-ttu-id="e38a3-350">Существует ряд различных областей действия ресурсов. Некоторые из них перечислены ниже в порядке их разрешения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-350">There are a variety of resource scopes, including the following, listed in the order in which they are resolved:</span></span>

1. <span data-ttu-id="e38a3-351">Отдельный элемент управления (с использованием наследуемого свойства <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="e38a3-351">An individual control (using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

2. <span data-ttu-id="e38a3-352"><xref:System.Windows.Window> или <xref:System.Windows.Controls.Page> (также с использованием наследуемого свойства <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="e38a3-352">A <xref:System.Windows.Window> or a <xref:System.Windows.Controls.Page> (also using the inherited <xref:System.Windows.FrameworkElement.Resources%2A?displayProperty=fullName> property).</span></span>

3. <span data-ttu-id="e38a3-353"><xref:System.Windows.Application> (с использованием свойства <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> ).</span><span class="sxs-lookup"><span data-stu-id="e38a3-353">An <xref:System.Windows.Application> (using the <xref:System.Windows.Application.Resources%2A?displayProperty=fullName> property).</span></span>

<span data-ttu-id="e38a3-354">Разнообразие областей действия обеспечивает гибкость в отношении способов определения ресурсов и предоставления доступа к ним.</span><span class="sxs-lookup"><span data-stu-id="e38a3-354">The variety of scopes gives you flexibility with respect to the way in which you define and share your resources.</span></span>

<span data-ttu-id="e38a3-355">Помимо прямого сопоставления ресурсов с определенной областью действия, можно упаковать один или несколько ресурсов с помощью отдельного объекта <xref:System.Windows.ResourceDictionary> , на который можно ссылаться в других частях приложения.</span><span class="sxs-lookup"><span data-stu-id="e38a3-355">As an alternative to directly associating your resources with a particular scope, you can package one or more resources by using a separate <xref:System.Windows.ResourceDictionary> that can be referenced in other parts of an application.</span></span> <span data-ttu-id="e38a3-356">Например, в следующем примере определяется цвет фона по умолчанию в словаре ресурсов.</span><span class="sxs-lookup"><span data-stu-id="e38a3-356">For example, the following example defines a default background color in a resource dictionary:</span></span>

```xaml
<ResourceDictionary
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">

  <!-- Define background color resource -->
  <SolidColorBrush x:Key="defaultBackground" Color="Red" />

  <!-- Define other resources -->
</ResourceDictionary>
```

<span data-ttu-id="e38a3-357">Следующий пример ссылается на словарь ресурсов, определенный в предыдущем примере, чтобы сделать его общим для приложения:</span><span class="sxs-lookup"><span data-stu-id="e38a3-357">The following example references the resource dictionary defined in the previous example so that it is shared across an application:</span></span>

```xaml
<Application
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.App">

  <Application.Resources>
    <ResourceDictionary>
      <ResourceDictionary.MergedDictionaries>
        <ResourceDictionary Source="BackgroundColorResources.xaml"/>
      </ResourceDictionary.MergedDictionaries>
    </ResourceDictionary>
  </Application.Resources>
</Application>
```

<span data-ttu-id="e38a3-358">Ресурсы и словари ресурсов лежат в основе реализованной в WPF поддержки тем и обложек.</span><span class="sxs-lookup"><span data-stu-id="e38a3-358">Resources and resource dictionaries are the foundation of WPF support for themes and skins.</span></span>

<span data-ttu-id="e38a3-359">Дополнительные сведения см. в статье о [ресурсах DSC](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-359">For more information, see [Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>

### <a name="custom-controls"></a><span data-ttu-id="e38a3-360">Пользовательские элементы управления</span><span class="sxs-lookup"><span data-stu-id="e38a3-360">Custom controls</span></span>

<span data-ttu-id="e38a3-361">Хотя WPF предоставляет множество возможностей настройки, могут возникнуть ситуации, когда существующие элементы управления WPF не удовлетворяют потребности вашего приложения или его пользователей.</span><span class="sxs-lookup"><span data-stu-id="e38a3-361">Although WPF provides a host of customization support, you may encounter situations where existing WPF controls do not meet the needs of either your application or its users.</span></span> <span data-ttu-id="e38a3-362">Это может произойти в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="e38a3-362">This can occur when:</span></span>

- <span data-ttu-id="e38a3-363">Требуемый пользовательский интерфейс нельзя создать, настроив внешний вид существующих элементов, реализованных в WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-363">The user interface that you require cannot be created by customizing the look and feel of existing WPF implementations.</span></span>

- <span data-ttu-id="e38a3-364">Требуемое поведение не поддерживается существующими элементами, реализованными в WPF, или его поддержка представляет трудность.</span><span class="sxs-lookup"><span data-stu-id="e38a3-364">The behavior that you require is not supported (or not easily supported) by existing WPF implementations.</span></span>

<span data-ttu-id="e38a3-365">В такой ситуации вы можете воспользоваться одной из трех моделей WPF, чтоб создать новый элемент управления.</span><span class="sxs-lookup"><span data-stu-id="e38a3-365">At this point, however, you can take advantage of one of three WPF models to create a new control.</span></span> <span data-ttu-id="e38a3-366">Каждая модель предназначена для определенного сценария и предполагает, что пользовательский элемент управления наследуется от определенного базового класса WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-366">Each model targets a specific scenario and requires your custom control to derive from a particular WPF base class.</span></span> <span data-ttu-id="e38a3-367">Ниже перечислены эти три модели.</span><span class="sxs-lookup"><span data-stu-id="e38a3-367">The three models are listed here:</span></span>

- <span data-ttu-id="e38a3-368">**Модель пользовательского элемента управления**.</span><span class="sxs-lookup"><span data-stu-id="e38a3-368">**User Control Model**.</span></span> <span data-ttu-id="e38a3-369">Пользовательский элемент управления наследуется от <xref:System.Windows.Controls.UserControl> и составляется из одного или нескольких других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="e38a3-369">A custom control derives from <xref:System.Windows.Controls.UserControl> and is composed of one or more other controls.</span></span>

- <span data-ttu-id="e38a3-370">**Модель элемента управления**.</span><span class="sxs-lookup"><span data-stu-id="e38a3-370">**Control Model**.</span></span> <span data-ttu-id="e38a3-371">Пользовательский элемент управления наследуется от <xref:System.Windows.Controls.Control> и используется для создания реализаций, в которых поведение и внешний вид разделяются с помощью шаблонов, как в большинстве элементов управления WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-371">A custom control derives from <xref:System.Windows.Controls.Control> and is used to build implementations that separate their behavior from their appearance using templates, much like the majority of WPF controls.</span></span> <span data-ttu-id="e38a3-372">Наследование от класса <xref:System.Windows.Controls.Control> обеспечивает большую гибкость при создании собственного пользовательского интерфейса, чем пользовательские элементы управления, но может потребовать больших усилий.</span><span class="sxs-lookup"><span data-stu-id="e38a3-372">Deriving from <xref:System.Windows.Controls.Control> allows you more freedom for creating a custom user interface than user controls, but it may require more effort.</span></span>

- <span data-ttu-id="e38a3-373">**Модель элемента платформы**.</span><span class="sxs-lookup"><span data-stu-id="e38a3-373">**Framework Element Model**.</span></span> <span data-ttu-id="e38a3-374">Пользовательский элемент управления наследуется от класса <xref:System.Windows.FrameworkElement> , если его внешний вид определяется пользовательской логикой отрисовки, а не шаблонами.</span><span class="sxs-lookup"><span data-stu-id="e38a3-374">A custom control derives from <xref:System.Windows.FrameworkElement> when its appearance is defined by custom rendering logic (not templates).</span></span>

<span data-ttu-id="e38a3-375">В следующем примере показан настраиваемый числовой элемент управления "вверх/вниз", производный от <xref:System.Windows.Controls.UserControl> :</span><span class="sxs-lookup"><span data-stu-id="e38a3-375">The following example shows a custom numeric up/down control that derives from <xref:System.Windows.Controls.UserControl>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlMARKUP](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_33.xaml)]

[!code-csharp[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/csharp/wpf/introduction-to-wpf/introduction-to-wpf_34.cs)]
[!code-vb[IntroToWPFSnippets#UserControlCODEBEHIND1](~/samples/snippets/visualbasic/wpf/introduction-to-wpf/introduction-to-wpf_34.vb)]

<span data-ttu-id="e38a3-376">В следующем примере показан код XAML, необходимый для включения пользовательского элемента управления в <xref:System.Windows.Window> :</span><span class="sxs-lookup"><span data-stu-id="e38a3-376">The following example illustrates the XAML that is required to incorporate the user control into a <xref:System.Windows.Window>:</span></span>

[!code-xaml[IntroToWPFSnippets#UserControlWindowMARKUP1](~/samples/snippets/xaml/wpf/introduction-to-wpf/introduction-to-wpf_37.xaml)]

<span data-ttu-id="e38a3-377">На следующем рисунке показан `NumericUpDown` элемент управления, размещенный в <xref:System.Windows.Window> :</span><span class="sxs-lookup"><span data-stu-id="e38a3-377">The following figure shows the `NumericUpDown` control hosted in a <xref:System.Windows.Window>:</span></span>

![Настраиваемый UserControl](media/introduction-to-wpf/wpfintrofigure3.png)

<span data-ttu-id="e38a3-379">Дополнительные сведения о пользовательских элементах управления см. в разделе [Общие сведения о разработке управления](controls/control-authoring-overview.md).</span><span class="sxs-lookup"><span data-stu-id="e38a3-379">For more information on custom controls, see [Control authoring overview](controls/control-authoring-overview.md).</span></span>

## <a name="wpf-best-practices"></a><span data-ttu-id="e38a3-380">Рекомендации по использованию WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-380">WPF best practices</span></span>

<span data-ttu-id="e38a3-381">Как и любую другую платформу разработки, WPF можно использовать разными способами для получения нужного результата.</span><span class="sxs-lookup"><span data-stu-id="e38a3-381">As with any development platform, WPF can be used in a variety of ways to achieve the desired result.</span></span> <span data-ttu-id="e38a3-382">Чтобы ваши приложения WPF обеспечивали требуемый уровень удобства и отвечали потребностям пользователей в целом, следует придерживаться рекомендаций в отношении специальных возможностей, глобализации, локализации и производительности.</span><span class="sxs-lookup"><span data-stu-id="e38a3-382">As a way of ensuring that your WPF applications provide the required user experience and meet the demands of the audience in general, there are recommended best practices for accessibility, globalization and localization, and performance.</span></span> <span data-ttu-id="e38a3-383">Дополнительные сведения можно найти в разделе</span><span class="sxs-lookup"><span data-stu-id="e38a3-383">For more information, see:</span></span>

- [<span data-ttu-id="e38a3-384">Специальные возможности</span><span class="sxs-lookup"><span data-stu-id="e38a3-384">Accessibility</span></span>](../ui-automation/accessibility-best-practices.md)
- [<span data-ttu-id="e38a3-385">Глобализация и локализация WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-385">WPF globalization and localization</span></span>](advanced/wpf-globalization-and-localization-overview.md)
- [<span data-ttu-id="e38a3-386">Производительность приложения WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-386">WPF app performance</span></span>](advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="e38a3-387">Безопасность WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-387">WPF security</span></span>](security-wpf.md)

## <a name="next-steps"></a><span data-ttu-id="e38a3-388">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="e38a3-388">Next steps</span></span>

<span data-ttu-id="e38a3-389">Мы рассмотрели основные возможности WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-389">We've looked at the key features of WPF.</span></span> <span data-ttu-id="e38a3-390">Теперь пора приступить к созданию первого приложения WPF.</span><span class="sxs-lookup"><span data-stu-id="e38a3-390">Now it's time to build your first WPF app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="e38a3-391">Пошаговое руководство. Создание первого классического приложения WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-391">Walkthrough: My first WPF desktop app</span></span>](getting-started/walkthrough-my-first-wpf-desktop-application.md)

## <a name="see-also"></a><span data-ttu-id="e38a3-392">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="e38a3-392">See also</span></span>

- [<span data-ttu-id="e38a3-393">Начало работы с WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-393">Get started with WPF</span></span>](getting-started/index.md)
- [<span data-ttu-id="e38a3-394">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="e38a3-394">Windows Presentation Foundation</span></span>](index.md)
- [<span data-ttu-id="e38a3-395">Ресурсы сообщества WPF</span><span class="sxs-lookup"><span data-stu-id="e38a3-395">WPF community resources</span></span>](getting-started/community-feedback.md)
