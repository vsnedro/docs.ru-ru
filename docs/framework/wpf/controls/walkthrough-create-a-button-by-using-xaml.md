---
title: Пошаговое руководство. Создание кнопки с помощью XAML
ms.date: 03/30/2017
helpviewer_keywords:
- buttons [WPF]
ms.assetid: 138c41c4-1759-4bbf-8d77-77031a06a8a0
ms.openlocfilehash: a8cc227703e81e5de9dea7e44e10dfecca2cd05c
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646467"
---
# <a name="walkthrough-create-a-button-by-using-xaml"></a>Пошаговое руководство. Создание кнопки с помощью XAML

Цель этого пошагового представления состоит в том, чтобы узнать, как создать анимированную кнопку для использования в приложении Windows Presentation Foundation (WPF). В этом пошаговом пошаговом использовании стилей и шаблона используется индивидуальный ресурс кнопок, который позволяет повторно использовать код и отделить логику кнопки от объявления кнопки. Это пошаговое [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]походе написано полностью в .

> [!IMPORTANT]
> Это пошаговое руководство проведет вас через шаги для создания [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] приложения, введя или копируя и вставляя в Visual Studio. Если вы предпочитаете научиться использовать конструктор для создания одного и того же приложения, [см.](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)

На следующем рисунке показаны готовые кнопки.

![Пользовательские кнопки, созданные с помощью XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-basic-buttons"></a>Создание базовых кнопок

Начнем с создания нового проекта и добавления нескольких кнопок в окно.

### <a name="to-create-a-new-wpf-project-and-add-buttons-to-the-window"></a>Создать новый проект WPF и добавить кнопки в окно

1. Запустите среду Visual Studio.

2. **Создание нового проекта WPF:** В меню **файла,** укажите на **новый**, а затем нажмите **проекта**. Найдите шаблон **приложения Windows (WPF)** и назовите проект "AnimatedButton". Это создаст скелет для приложения.

3. **Добавьте основные кнопки по умолчанию:** Все файлы, необходимые для этого пошагового покрешение, предоставляются шаблоном. Откройте файл Window1.xaml, дважды нажав на него в Solution Explorer. По умолчанию в <xref:System.Windows.Controls.Grid> Window1.xaml есть элемент. Удалите <xref:System.Windows.Controls.Grid> элемент и добавьте [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] несколько кнопок на страницу, введя или скопив и вставив следующий выделенный код в Window1.xaml:

    ```xaml
    <Window x:Class="AnimatedButton.Window1"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      Title="AnimatedButton" Height="300" Width="300"
      Background="Black">
      <!-- Buttons arranged vertically inside a StackPanel. -->
      <StackPanel HorizontalAlignment="Left">
          <Button>Button 1</Button>
          <Button>Button 2</Button>
          <Button>Button 3</Button>
      </StackPanel>
    </Window>
    ```

     Нажмите F5 для запуска приложения; вы должны увидеть набор кнопок, который выглядит как следующая цифра.

     ![Три основные кнопки](./media/custom-button-animatedbutton-1.gif "custom_button_AnimatedButton_1")

     Теперь, когда вы создали основные кнопки, вы закончили работать в файле Window1.xaml. Остальная часть пошагового промотина фокусируется на файле app.xaml, определяя стили и шаблон для кнопок.

## <a name="set-basic-properties"></a>Набор основных свойств

Далее давайте установить некоторые свойства на этих кнопках для управления появлением и макетом кнопки. Вместо того, чтобы устанавливать свойства на кнопках по отдельности, вы будете использовать ресурсы для определения свойств кнопок для всего приложения. Ресурсы приложений концептуально аналогичны внешним Каскадным стилям листов (CSS) для веб-страниц; однако, ресурсы гораздо более мощные, чем Каскадные листы стиля (CSS), как вы увидите к концу этого пошагового листа. Чтобы узнать больше о ресурсах, [см.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)

### <a name="to-use-styles-to-set-basic-properties-on-the-buttons"></a>Использовать стили для установки основных свойств на кнопках

1. **Определите блок Application.Resources:** Откройте app.xaml и добавьте следующую выделенную разметку, если она еще не существует:

    ```xaml
    <Application x:Class="AnimatedButton.App"
      xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
      xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
      StartupUri="Window1.xaml"
      >
      <Application.Resources>
        <!-- Resources for the entire application can be defined here. -->
      </Application.Resources>
    </Application>
    ```

     Область ресурсов определяется по тому, где вы определяете ресурс. Определение ресурсов `Application.Resources` в файле app.xaml позволяет использовать ресурс из любой точки приложения. Подробнее об определении объема ресурсов [можно](../../../desktop-wpf/fundamentals/xaml-resources-define.md)узнать на см.

2. **Создайте стиль и определите основные значения свойства с его помощью:** Добавьте следующую разметку в `Application.Resources` блок. Эта разметка <xref:System.Windows.Style> создает, что применяется ко всем <xref:System.Windows.FrameworkElement.Width%2A> кнопкам в приложении, <xref:System.Windows.FrameworkElement.Margin%2A> установив кнопки до 90 и до 10:

    ```xaml
    <Application.Resources>
      <Style TargetType="Button">
        <Setter Property="Width" Value="90" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Свойство <xref:System.Windows.Style.TargetType%2A> указывает, что стиль применяется ко всем <xref:System.Windows.Controls.Button>объектам типа. Каждый <xref:System.Windows.Setter> устанавливает различное <xref:System.Windows.Style>значение свойства для . Поэтому на данный момент каждая кнопка в приложении имеет ширину 90 и маржу 10.  Если вы нажмете F5 для запуска приложения, вы увидите следующее окно.

     ![Кнопки с шириной равной 90 и границей 10](./media/custom-button-animatedbutton-2.gif "custom_button_AnimatedButton_2")

     Существует гораздо больше, вы можете сделать со стилями, в том числе различные способы точной настройки объектов, указывая сложные значения свойств, и даже с помощью стилей в качестве ввода для других стилей. Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

3. **Установите значение свойства стиля ресурсу:** Ресурсы позволяют использовать простой способ повторного использования общеоизвестных объектов и значений. Особенно полезно определить сложные значения, используя ресурсы, чтобы сделать ваш код более модульным. Добавьте следующую выделенную разметку в app.xaml.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush" StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
      </Style>
    </Application.Resources>
    ```

     Непосредственно под `Application.Resources` блоком, вы создали ресурс под названием "GrayBlueGradientBrush". Этот ресурс определяет горизонтальный градиент. Этот ресурс может быть использован в качестве свойства значение из любой точки <xref:System.Windows.Controls.Control.Background%2A> приложения, в том числе внутри кнопки стиль сеттер для свойства. Теперь все кнопки <xref:System.Windows.Controls.Control.Background%2A> имеют значение свойства этого градиента.

     Нажмите клавишу F5 для запуска приложения. Он должен выглядеть следующим образом.

     ![Кнопки с фоновым градиентом](./media/custom-button-animatedbutton-3.gif "custom_button_AnimatedButton_3")

## <a name="create-a-template-that-defines-the-look-of-the-button"></a>Создайте шаблон, определяющий внешний вид кнопки

В этом разделе вы создаете шаблон, который настраивает внешний вид (презентацию) кнопки. Презентация кнопки состоит из нескольких объектов, включая прямоугольники и другие компоненты, чтобы придать кнопке уникальный вид.

До сих пор контроль за тем, как выглядят кнопки в приложении, ограничивался изменением свойств кнопки. Что делать, если вы хотите внести более радикальные изменения в внешний вид кнопки? Шаблоны позволяют осуществлять мощный контроль над презентацией объекта. Поскольку шаблоны могут использоваться в стилях, можно применить шаблон ко всем объектам, к которым применяется стиль (в этом пошаговом шаге кнопка).

### <a name="to-use-the-template-to-define-the-look-of-the-button"></a>Использовать шаблон для определения вида кнопки

1. **Настройка шаблона:** Поскольку <xref:System.Windows.Controls.Button> элементы <xref:System.Windows.Controls.Control.Template%2A> управления, такие как свойство, можно определить значение свойства шаблона так же, как и другие значения свойств, которые мы установили в <xref:System.Windows.Style> использовании <xref:System.Windows.Setter>. Добавьте следующую выделенную разметку в стиль кнопки.

    ```xaml
    <Application.Resources>
      <LinearGradientBrush x:Key="GrayBlueGradientBrush"
        StartPoint="0,0" EndPoint="1,1">
        <GradientStop Color="DarkGray" Offset="0" />
        <GradientStop Color="#CCCCFF" Offset="0.5" />
        <GradientStop Color="DarkGray" Offset="1" />
      </LinearGradientBrush>
      <Style TargetType="{x:Type Button}">
        <Setter Property="Background" Value="{StaticResource GrayBlueGradientBrush}" />
        <Setter Property="Width" Value="80" />
        <Setter Property="Margin" Value="10" />
        <Setter Property="Template">
          <Setter.Value>
            <!-- The button template is defined here. -->
          </Setter.Value>
        </Setter>
      </Style>
    </Application.Resources>
    ```

2. **Презентация кнопки Alter:** На этом этапе необходимо определить шаблон. Добавьте следующую выделенную разметку. Эта разметка определяет <xref:System.Windows.Shapes.Rectangle> два элемента с закруглеными краями, а затем <xref:System.Windows.Controls.DockPanel>. Используется <xref:System.Windows.Controls.DockPanel> для размещения <xref:System.Windows.Controls.ContentPresenter> кнопки. Содержимое <xref:System.Windows.Controls.ContentPresenter> кнопки отображается. В этом пошаговом шаге, содержание текста ("Кнопка 1", "Кнопка 2", "Кнопка 3"). Все компоненты шаблона (прямоугольники <xref:System.Windows.Controls.DockPanel>и) выложены <xref:System.Windows.Controls.Grid>внутри .

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="Button">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}" ClipToBounds="True">
          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}" RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />
          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch" VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20" Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />
          <!-- Present Content (text) of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20" Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>
      </ControlTemplate>
    </Setter.Value>
    ```

     Нажмите клавишу F5 для запуска приложения. Он должен выглядеть следующим образом.

     ![Окно с 3 кнопками](./media/custom-button-animatedbutton-4.gif)

3. **Добавьте стеклоэффект в шаблон:** Далее вы добавите стакан. Сначала вы создаете некоторые ресурсы, которые создают эффект градиента стекла. Добавьте эти ресурсы `Application.Resources` градиента в любом месте блока:

    ```xaml
    <Application.Resources>
      <GradientStopCollection x:Key="MyGlassGradientStopsResource">
        <GradientStop Color="WhiteSmoke" Offset="0.2" />
        <GradientStop Color="Transparent" Offset="0.4" />
        <GradientStop Color="WhiteSmoke" Offset="0.5" />
        <GradientStop Color="Transparent" Offset="0.75" />
        <GradientStop Color="WhiteSmoke" Offset="0.9" />
        <GradientStop Color="Transparent" Offset="1" />
      </GradientStopCollection>
      <LinearGradientBrush x:Key="MyGlassBrushResource"
        StartPoint="0,0" EndPoint="1,1" Opacity="0.75"
        GradientStops="{StaticResource MyGlassGradientStopsResource}" />
    <!-- Styles and other resources below here. -->
    ```

     Эти ресурсы используются в <xref:System.Windows.Shapes.Shape.Fill%2A> качестве прямоугольника, <xref:System.Windows.Controls.Grid> который мы вставляем в шаблон кнопки. Добавьте в шаблон следующую выделенную разметку.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}" Height="{TemplateBinding Height}"
          ClipToBounds="True">

        <!-- Outer Rectangle with rounded corners. -->
        <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

        <!-- Inner Rectangle with rounded corners. -->
        <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="Transparent" StrokeThickness="20"
          Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20" />

        <!-- Glass Rectangle -->
        <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch"
          StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
          Fill="{StaticResource MyGlassBrushResource}"
          RenderTransformOrigin="0.5,0.5">
          <Rectangle.Stroke>
            <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
              <LinearGradientBrush.GradientStops>
                <GradientStop Offset="0.0" Color="LightBlue" />
                <GradientStop Offset="1.0" Color="Gray" />
              </LinearGradientBrush.GradientStops>
            </LinearGradientBrush>
          </Rectangle.Stroke>
          <!-- These transforms have no effect as they are declared here.
          The reason the transforms are included is to be targets
          for animation (see later). -->
          <Rectangle.RenderTransform>
            <TransformGroup>
              <ScaleTransform />
              <RotateTransform />
            </TransformGroup>
          </Rectangle.RenderTransform>
          <!-- A BevelBitmapEffect is applied to give the button a "Beveled" look. -->
          <Rectangle.BitmapEffect>
            <BevelBitmapEffect />
          </Rectangle.BitmapEffect>
        </Rectangle>

        <!-- Present Text of the button. -->
        <DockPanel Name="myContentPresenterDockPanel">
          <ContentPresenter x:Name="myContentPresenter" Margin="20"
            Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
        </DockPanel>
      </Grid>
    </ControlTemplate>
    </Setter.Value>
    ```

     Обратите внимание, что <xref:System.Windows.UIElement.Opacity%2A> прямоугольник `x:Name` с свойством "glassCube" составляет 0, поэтому при запуске образца, вы не видите стеклянный прямоугольник накладывается на вершине. Это происходит потому, что мы позже добавим триггеры в шаблон, когда пользователь взаимодействует с кнопкой. Тем не менее, вы можете увидеть, <xref:System.Windows.UIElement.Opacity%2A> как сейчас выглядит кнопка, изменив значение на 1 и запустив приложение. См. следующий рисунок. Прежде чем перейти к следующему шагу, измените <xref:System.Windows.UIElement.Opacity%2A> обратно на 0.

     ![Пользовательские кнопки, созданные с помощью XAML](./media/custom-button-animatedbutton-5.gif "custom_button_AnimatedButton_5")

## <a name="create-button-interactivity"></a>Создание интерактивности кнопки

В этом разделе вы создадите триггеры свойств и триггеры событий для изменения значений свойств и запуска анимации в ответ на действия пользователя, такие как перемещение указателя мыши по кнопке и нажатие кнопки.

Простой способ добавить интерактивность (мышь-за, мышь-оставить, нажмите, и так далее) заключается в определении триггеров в шаблоне или стиле. Для создания <xref:System.Windows.Trigger>, вы определяете свойство "условие", такие как: Значение свойства кнопки <xref:System.Windows.UIElement.IsMouseOver%2A> `true`равна. Затем вы определяете сеттеры (действия), которые происходят, когда условие триггера верно.

### <a name="to-create-button-interactivity"></a>Для создания интерактивности кнопок

1. **Добавить триггеры шаблонов:** Добавьте выделенную разметку в шаблон.

    ```xaml
    <Setter.Value>
      <ControlTemplate TargetType="{x:Type Button}">
        <Grid Width="{TemplateBinding Width}"
          Height="{TemplateBinding Height}" ClipToBounds="True">

          <!-- Outer Rectangle with rounded corners. -->
          <Rectangle x:Name="outerRectangle" HorizontalAlignment="Stretch"
          VerticalAlignment="Stretch" Stroke="{TemplateBinding Background}"
          RadiusX="20" RadiusY="20" StrokeThickness="5" Fill="Transparent" />

          <!-- Inner Rectangle with rounded corners. -->
          <Rectangle x:Name="innerRectangle" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch" Stroke="Transparent"
            StrokeThickness="20"
            Fill="{TemplateBinding Background}" RadiusX="20" RadiusY="20"
          />

          <!-- Glass Rectangle -->
          <Rectangle x:Name="glassCube" HorizontalAlignment="Stretch"
            VerticalAlignment="Stretch"
            StrokeThickness="2" RadiusX="10" RadiusY="10" Opacity="0"
            Fill="{StaticResource MyGlassBrushResource}"
            RenderTransformOrigin="0.5,0.5">
            <Rectangle.Stroke>
              <LinearGradientBrush StartPoint="0.5,0" EndPoint="0.5,1">
                <LinearGradientBrush.GradientStops>
                  <GradientStop Offset="0.0" Color="LightBlue" />
                  <GradientStop Offset="1.0" Color="Gray" />
                </LinearGradientBrush.GradientStops>
              </LinearGradientBrush>
            </Rectangle.Stroke>

            <!-- These transforms have no effect as they
                 are declared here.
                 The reason the transforms are included is to be targets
                 for animation (see later). -->
            <Rectangle.RenderTransform>
              <TransformGroup>
                <ScaleTransform />
                <RotateTransform />
              </TransformGroup>
            </Rectangle.RenderTransform>

              <!-- A BevelBitmapEffect is applied to give the button a
                   "Beveled" look. -->
            <Rectangle.BitmapEffect>
              <BevelBitmapEffect />
            </Rectangle.BitmapEffect>
          </Rectangle>

          <!-- Present Text of the button. -->
          <DockPanel Name="myContentPresenterDockPanel">
            <ContentPresenter x:Name="myContentPresenter" Margin="20"
              Content="{TemplateBinding  Content}" TextBlock.Foreground="Black" />
          </DockPanel>
        </Grid>

        <ControlTemplate.Triggers>       <!-- Set action triggers for the buttons and define            what the button does in response to those triggers. -->     </ControlTemplate.Triggers>
      </ControlTemplate>
    </Setter.Value>
    ```

2. **Добавить триггеры свойств:** Добавьте выделенную разметку в `ControlTemplate.Triggers` блок:

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->   <Trigger Property="IsMouseOver" Value="True">     <!-- Below are three property settings that occur when the           condition is met (user mouses over button).  -->     <!-- Change the color of the outer rectangle when user           mouses over it. -->     <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <!-- Sets the glass opacity to 1, therefore, the           glass "appears" when user mouses over it. -->     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />     <!-- Makes the text slightly blurry as though you           were looking at it through blurry glass. -->     <Setter Property="ContentPresenter.BitmapEffect"        TargetName="myContentPresenter">       <Setter.Value>         <BlurBitmapEffect Radius="1" />       </Setter.Value>     </Setter>   </Trigger>

    <ControlTemplate.Triggers/>
    ```

     Нажмите F5, чтобы запустить приложение и увидеть эффект, как вы запустите указатель мыши над кнопками.

3. **Добавить триггер фокусировки:** Далее мы добавим несколько аналогичных сеттеров для обработки случая, когда кнопка имеет фокус (например, после того, как пользователь нажмет его).

    ```xaml
    <ControlTemplate.Triggers>

      <!-- Set properties when mouse pointer is over the button. -->
      <Trigger Property="IsMouseOver" Value="True">

        <!-- Below are three property settings that occur when the
             condition is met (user mouses over button).  -->
        <!-- Change the color of the outer rectangle when user          mouses over it. -->
        <Setter Property ="Rectangle.Stroke" TargetName="outerRectangle"
          Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />

        <!-- Sets the glass opacity to 1, therefore, the          glass "appears" when user mouses over it. -->
        <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />

        <!-- Makes the text slightly blurry as though you were          looking at it through blurry glass. -->
        <Setter Property="ContentPresenter.BitmapEffect"       TargetName="myContentPresenter">
          <Setter.Value>
            <BlurBitmapEffect Radius="1" />
          </Setter.Value>
        </Setter>
      </Trigger>
      <!-- Set properties when button has focus. -->   <Trigger Property="IsFocused" Value="true">     <Setter Property="Rectangle.Opacity" Value="1"       TargetName="glassCube" />     <Setter Property="Rectangle.Stroke" TargetName="outerRectangle"       Value="{DynamicResource {x:Static SystemColors.HighlightBrushKey}}" />     <Setter Property="Rectangle.Opacity" Value="1" TargetName="glassCube" />   </Trigger>

    </ControlTemplate.Triggers>
    ```

     Нажмите F5, чтобы запустить приложение и нажмите на одну из кнопок. Обратите внимание, что кнопка остается выделенной после нажатия на нее, потому что она по-прежнему имеет фокус. Если вы нажмете другую кнопку, новая кнопка получает фокус, в то время как последняя теряет ее.

4. **Добавить анимации для** <xref:System.Windows.UIElement.MouseEnter> **и** <xref:System.Windows.UIElement.MouseLeave> **:** Далее мы добавляем некоторые анимации на триггеры.   Добавьте следующую разметку `ControlTemplate.Triggers` в любом месте внутри блока.

    ```xaml
    <!-- Animations that start when mouse enters and leaves button. -->
    <EventTrigger RoutedEvent="Mouse.MouseEnter">
      <EventTrigger.Actions>
        <BeginStoryboard Name="mouseEnterBeginStoryboard">
          <Storyboard>
          <!-- This animation makes the glass rectangle shrink in the X direction. -->
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleX)"
              By="-0.1" Duration="0:0:0.5" />
            <!-- This animation makes the glass rectangle shrink in the Y direction. -->
            <DoubleAnimation
            Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[0].(ScaleTransform.ScaleY)"
              By="-0.1" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    <EventTrigger RoutedEvent="Mouse.MouseLeave">
      <EventTrigger.Actions>
        <!-- Stopping the storyboard sets all animated properties back to default. -->
        <StopStoryboard BeginStoryboardName="mouseEnterBeginStoryboard" />
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Стеклянный прямоугольник сжимается, когда указатель мыши перемещается по кнопке и возвращается к нормальному размеру, когда указатель уходит.

     Есть две анимации, которые срабатывают, когда<xref:System.Windows.UIElement.MouseEnter> указатель переходит кнопку (событие поднято). Эти анимации сокращают стеклянный прямоугольник вдоль оси X и Y. Обратите внимание на <xref:System.Windows.Media.Animation.DoubleAnimation> свойства <xref:System.Windows.Media.Animation.Timeline.Duration%2A> <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A>на элементы - и . Указывается, <xref:System.Windows.Media.Animation.Timeline.Duration%2A> что анимация происходит более половины <xref:System.Windows.Media.Animation.DoubleAnimation.By%2A> секунды, и указывает, что стекло сжимается на 10%.

     Второй триггер события<xref:System.Windows.UIElement.MouseLeave>() просто останавливает первый. При остановке <xref:System.Windows.Media.Animation.Storyboard>все анимированные свойства возвращаются к значениям по умолчанию. Поэтому, когда пользователь перемещает указатель с кнопки, кнопка возвращается к тому, как это было до указателя мыши переехал над кнопкой. Для получения дополнительной информации об анимации, [см.](../graphics-multimedia/animation-overview.md)

5. **Добавьте анимацию при нажатии кнопки:** Последним шагом является добавление триггера, когда пользователь нажимает на кнопку. Добавьте следующую разметку `ControlTemplate.Triggers` в любом месте блока:

    ```xaml
    <!-- Animation fires when button is clicked, causing glass to spin.  -->
    <EventTrigger RoutedEvent="Button.Click">
      <EventTrigger.Actions>
        <BeginStoryboard>
          <Storyboard>
            <DoubleAnimation Storyboard.TargetName="glassCube"
              Storyboard.TargetProperty=
              "(Rectangle.RenderTransform).(TransformGroup.Children)[1].(RotateTransform.Angle)"
              By="360" Duration="0:0:0.5" />
          </Storyboard>
        </BeginStoryboard>
      </EventTrigger.Actions>
    </EventTrigger>
    ```

     Нажмите F5, чтобы запустить приложение, и нажмите одну из кнопок. При нажатии кнопки стеклянный прямоугольник вращается вокруг.

## <a name="summary"></a>Сводка
 В этом пошаговом шаге вы выполнили следующие упражнения:

- Целевой <xref:System.Windows.Style> тип объекта ().<xref:System.Windows.Controls.Button>

- Управляемые основные свойства кнопок <xref:System.Windows.Style>во всем приложении с помощью .

- Созданные ресурсы, такие как градиенты для использования значений <xref:System.Windows.Style> свойств сеттеров.

- Настроил внешний вид кнопок во всем приложении, применяя шаблон к кнопкам.

- Индивидуальное поведение для кнопок в ответ <xref:System.Windows.UIElement.MouseEnter> <xref:System.Windows.UIElement.MouseLeave>на <xref:System.Windows.Controls.Primitives.ButtonBase.Click>действия пользователя (например, и), которые включали эффекты анимации.

## <a name="see-also"></a>См. также раздел

- [Создание кнопки с помощью Microsoft Expression Blend](walkthrough-create-a-button-by-using-microsoft-expression-blend.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Общие сведения об эффектах анимации](../graphics-multimedia/animation-overview.md)
- [Общие сведения о закраске сплошным цветом и градиентом](../graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
- [Общие сведения об эффектах для точечных рисунков](../graphics-multimedia/bitmap-effects-overview.md)
