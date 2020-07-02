---
title: Практическое руководство. Определение всплывающих подсказок для элементов управления в Windows Forms во время разработки
description: Сведения о настройке подсказок для элементов управления программным способом или в конструктор Windows Forms в Visual Studio.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 144ba5b6bffb4a538e345f7b2df4a453fc6fd63d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618029"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a>Как задать подсказки для элементов управления в форме Windows во время разработки

Строку можно задать <xref:System.Windows.Forms.ToolTip> в коде или в конструктор Windows Forms в Visual Studio. Дополнительные сведения о <xref:System.Windows.Forms.ToolTip> компоненте см. в разделе [Общие сведения о компоненте ToolTip](tooltip-component-overview-windows-forms.md).

## <a name="set-a-tooltip-programmatically"></a>Программное задание подсказки

1. Добавьте элемент управления, который будет отображать подсказку.

2. Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.

    ```vb
    ' In this example, Button1 is the control to display the ToolTip.
    ToolTip1.SetToolTip(Button1, "Save changes")
    ```

    ```csharp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1.SetToolTip(button1, "Save changes");
    ```

    ```cpp
    // In this example, button1 is the control to display the ToolTip.
    toolTip1->SetToolTip(button1, "Save changes");
    ```

## <a name="set-a-tooltip-in-the-designer"></a>Задание подсказки в конструкторе

1. В Visual Studio добавьте компонент в <xref:System.Windows.Forms.ToolTip> форму.

2. Выберите элемент управления, который будет отображать подсказку, или добавьте его в форму.

3. В окне " **Свойства** " установите **подсказку для значения ToolTip1** в соответствующую строку текста.

### <a name="to-remove-a-tooltip-programmatically"></a>Удаление подсказки программными средствами

1. Используйте <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> метод <xref:System.Windows.Forms.ToolTip> компонента.

    ```vb
    ' In this example, Button1 is the control displaying the ToolTip.
    ToolTip1.SetToolTip(Button1, Nothing)
    ```

    ```csharp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1.SetToolTip(button1, null);
    ```

    ```cpp
    // In this example, button1 is the control displaying the ToolTip.
    toolTip1->SetToolTip(button1, NULL);
    ```

## <a name="remove-a-tooltip-in-the-designer"></a>Удаление подсказки в конструкторе

1. В Visual Studio выберите элемент управления, отображающий подсказку.

2. В окне **Свойства** удалите текст из **подсказки в ToolTip1**.

## <a name="see-also"></a>См. также

- [Общие сведения об элементе управления ToolTip](tooltip-component-overview-windows-forms.md)
- [Практическое руководство. Изменение значения задержки для компонента ToolTip в Windows Forms](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [Компонент ToolTip](tooltip-component-windows-forms.md)
