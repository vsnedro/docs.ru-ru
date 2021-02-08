---
description: 'Дополнительные сведения: Пользовательские составные конструкторы — представление элементов рабочего процесса'
title: Пользовательские составные конструкторы - средство представления элементов рабочего процесса
ms.date: 03/30/2017
ms.assetid: f85224cf-9e30-44a5-9a81-3bc438a34364
ms.openlocfilehash: 20a3bddf7efd69b6138d6b8a5caae250aa377999
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787816"
---
# <a name="custom-composite-designers---workflow-item-presenter"></a>Пользовательские составные конструкторы - средство представления элементов рабочего процесса

<xref:System.Activities.Presentation.WorkflowItemPresenter>— Это тип ключа в модели программирования КОНСТРУКТОРА WF, который позволяет создавать "Drop Zone", где можно разместить произвольное действие. В этом образце показано, как создать конструктор действий, который охватывает такую "область перетаскивания".

В этом примере демонстрируются следующее:

- Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.

- Регистрация пользовательского конструктора с использованием хранилища метаданных.

- Программирование повторно размещенной области элементов декларативно и принудительно.

## <a name="sample-details"></a>Подробные сведения об образце

Код для этого образца показывает следующее:

- Для класса `SimpleNativeActivity` создается конструктор пользовательских действий.

- Создание настраиваемого конструктора действий с <xref:System.Activities.Presentation.WorkflowItemPresenter>.

```xaml
<sap:ActivityDesigner x:Class="Microsoft.Samples.UsingWorkflowItemPresenter.SimpleNativeDesigner"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:sap="clr-namespace:System.Activities.Presentation;assembly=System.Activities.Presentation"
    xmlns:sapv="clr-namespace:System.Activities.Presentation.View;assembly=System.Activities.Presentation">
    <sap:ActivityDesigner.Resources>
        <DataTemplate x:Key="Collapsed">
            <StackPanel>
                <TextBlock>This is the collapsed view</TextBlock>
            </StackPanel>
        </DataTemplate>
        <DataTemplate x:Key="Expanded">
            <StackPanel>
                <TextBlock>Custom Text</TextBlock>
                <sap:WorkflowItemPresenter Item="{Binding Path=ModelItem.Body, Mode=TwoWay}"
                                        HintText="Please drop an activity here" />
            </StackPanel>
        </DataTemplate>
        <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
            <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
            <Style.Triggers>
                <DataTrigger Binding="{Binding Path=ShowExpanded}" Value="true">
                    <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
                </DataTrigger>
            </Style.Triggers>
        </Style>
    </sap:ActivityDesigner.Resources>
    <Grid>
        <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}" />
    </Grid>
</sap:ActivityDesigner>
```

 Обратите внимание на использование привязки данных WPF для привязки к `ModelItem.Body`. `ModelItem` — Это свойство <xref:System.Activities.Presentation.ActivityDesigner> , которое ссылается на базовый объект, для которого используется конструктор, в данном случае **симпленативеактивити**.

## <a name="set-up-build-and-run-the-sample"></a>Настройка, сборка и запуск примера

1. Откройте решение в Visual Studio.

2. Нажмите клавишу **F5** , чтобы скомпилировать и запустить приложение.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для платформа .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemPresenter`

## <a name="see-also"></a>См. также

- <xref:System.Activities.Presentation.WorkflowItemPresenter>
- [Разработка приложений с помощью конструктора рабочего процесса](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
