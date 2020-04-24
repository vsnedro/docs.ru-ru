---
title: 'Прохождение: Стиль WPF содержание'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 07241d41e3fbf270a76bd241765bfa369ee265d5
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646328"
---
# <a name="walkthrough-style-wpf-content"></a>Прохождение: Стиль WPF содержание

В этой статье показан, как применять стиль к управлению Windows Presentation Foundation (WPF), размещенном в форме Windows.

## <a name="prerequisites"></a>Предварительные требования

Для выполнения шагов, описанных в этом руководстве, вам понадобится Visual Studio.

## <a name="create-the-project"></a>Создание проекта

Откройте Visual Studio и создайте новый проект приложения `StylingWpfContent`Windows Forms в visual Basic или Visual C ' под названием .

> [!NOTE]
> При размещении содержимого WPF поддерживаются только проекты C# и Visual Basic.

## <a name="create-the-wpf-control-types"></a>Создание типов управления WPF

После добавления в проект типа элемента управления WPF можно разместить его в элементе управления <xref:System.Windows.Forms.Integration.ElementHost>.

1. Добавьте в решение новый проект WPF <xref:System.Windows.Controls.UserControl>. Используйте имя по умолчанию для этого типа элемента управления (`UserControl1.xaml`). Для получения дополнительной информации [см.](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)

2. Убедитесь в том, что элемент `UserControl1` выбран в представлении конструирования.

3. В окне **Свойств** установите <xref:System.Windows.FrameworkElement.Width%2A> значение <xref:System.Windows.FrameworkElement.Height%2A> и свойства до **200**.

4. Добавьте <xref:System.Windows.Controls.Button?displayProperty=nameWithType> элемент <xref:System.Windows.Controls.UserControl> управления в и <xref:System.Windows.Controls.ContentControl.Content%2A> установите значение свойства для **отмены.**

5. Добавьте <xref:System.Windows.Controls.Button?displayProperty=nameWithType> второй элемент <xref:System.Windows.Controls.UserControl> управления и установите значение <xref:System.Windows.Controls.ContentControl.Content%2A> свойства в **OK.**

6. Создайте проект.

## <a name="apply-a-style-to-a-wpf-control"></a>Примените стиль к управлению WPF

Для изменения внешнего вида и поведения элемента управления WPF к нему можно применить различные стили.

1. Откройте `Form1` в конструкторе Windows Forms.

1. В **Toolbox**, дважды `UserControl1` нажмите, `UserControl1` чтобы создать экземпляр на форме.

   Экземпляр `UserControl1` размещается в новом элементе управления <xref:System.Windows.Forms.Integration.ElementHost> с именем `elementHost1`.

1. В смарт-панели `elementHost1`тегов для , нажмите **Edit Hosted Содержание** из списка выпадающих вниз.

   `UserControl1`открывается в WPF Designer.

1. В представлении XAML вставьте следующий код XAML после открывающего тега `<UserControl>` . Этот код XAML создает градиент с контрастной градиентной границей. При нажатии на элемент управления градиенты изменяются, формируя образ нажатой кнопки. Более подробную информацию см. в разделе [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md).

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. Примените стиль, `SimpleButton` определенный в предыдущем шаге, к кнопке `<Button>` Отмена, вставив следующий XAML в тег кнопки **Отмена.**

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   Ваша кнопочно-разыскная декларация будет напоминать следующее XAML:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Создайте проект.

1. Откройте `Form1` в конструкторе Windows Forms.

1. Новый стиль применяется для элемента управления button.

1. Из меню **Debug** выберите **Start Debugging** для запуска приложения.

1. Нажмите кнопки **OK** и **Cancel** и просмотрите различия.

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Миграция и взаимодействие систем](../../wpf/advanced/migration-and-interoperability.md)
- [Использование элементов управления WPF](using-wpf-controls.md)
- [Проектирование XAML в Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
