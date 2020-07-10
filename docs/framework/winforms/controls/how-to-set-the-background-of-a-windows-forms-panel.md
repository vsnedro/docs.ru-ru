---
title: Установка фона панели
description: Узнайте, как задать цвет фона и фоновое изображение панели Windows Forms с помощью конструктора.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: 096cbd8d-45cc-47b8-b1ef-a27f60ea8be0
ms.openlocfilehash: 109ff6184de9c79d1576207bbeb29ad939670b6f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173384"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel"></a>Практическое руководство. Установка фона панели Windows Forms
<xref:System.Windows.Forms.Panel>Элемент управления Windows Forms может отображать как цвет фона, так и фоновое изображение. <xref:System.Windows.Forms.Control.BackColor%2A>Свойство задает цвет фона для вложенных элементов управления, таких как метки и переключатели. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство не задано, <xref:System.Windows.Forms.Control.BackColor%2A> Выделенная область будет заполнена всей панелью. Если <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство задано, изображение будет отображаться позади вложенных элементов управления.  
  
### <a name="to-set-the-background-programmatically"></a>Установка фонового рисунка программным способом  
  
1. Задайте <xref:System.Windows.Forms.Control.BackColor%2A> для свойства панели значение типа <xref:System.Drawing.Color?displayProperty=nameWithType> .  
  
    ```vb  
    Panel1.BackColor = Color.AliceBlue  
    ```  
  
    ```csharp  
    panel1.BackColor = Color.AliceBlue;  
    ```  
  
    ```cpp  
    panel1->BackColor = Color::AliceBlue;  
    ```  
  
2. Задайте <xref:System.Windows.Forms.Control.BackgroundImage%2A> свойство панели с помощью <xref:System.Drawing.Image.FromFile%2A> метода <xref:System.Drawing.Image?displayProperty=nameWithType> класса.  
  
    ```vb  
    ' You should replace the bolded image
    ' in the sample below with an image of your own choosing.  
    Panel1.BackgroundImage = Image.FromFile _  
        (System.Environment.GetFolderPath _  
        (System.Environment.SpecialFolder.Personal) _  
        & "\Image.gif")  
    ```  
  
    ```csharp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    panel1.BackgroundImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
    ```  
  
    ```cpp  
    // You should replace the bolded image
    // in the sample below with an image of your own choosing.  
    panel1->BackgroundImage = Image::FromFile(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\Image.gif"));  
    ```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [Элемент управления Panel](panel-control-windows-forms.md)
- [Общие сведения об элементе управления Panel](panel-control-overview-windows-forms.md)
