---
title: Задать порядок табуляции элементов управления
description: Узнайте, как задать порядок табуляции элементов управления в Windows Forms. Установите порядок табуляции в Visual Studio или используйте свойство TabIndex в окно свойств.
ms.date: 03/30/2017
f1_keywords:
- TabStop
- TabIndex
helpviewer_keywords:
- tab order [Windows Forms], controls on Windows forms
- Windows Forms controls, setting tab order
- controls [Windows Forms], setting tab order
- Windows Forms, setting tab order
ms.assetid: 71fa8e76-0472-414b-ad3c-0f90166e0ad7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 3d16da1ac73cc030b92bb36c4bfa3a79985339bf
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903366"
---
# <a name="how-to-set-the-tab-order-on-windows-forms"></a>Как задать порядок табуляции на Windows Forms

Порядок табуляции — это порядок, в котором пользователь перемещает фокус с одного элемента управления на другой, нажимая клавишу TAB. Каждая форма имеет собственный порядок табуляции. По умолчанию порядок табуляции совпадает с порядком, в котором были созданы элементы управления. Нумерация в порядке табуляции начинается с нуля.

## <a name="to-set-the-tab-order-of-a-control"></a>Установка последовательности табуляции элемента управления

1. В Visual Studio в меню **вид** выберите **последовательность табуляции**.

   Это активирует режим выбора порядка табуляции в форме. Число (представляющее <xref:System.Windows.Forms.Control.TabIndex%2A> свойство) отображается в левом верхнем углу каждого элемента управления.

2. Последовательно щелкните элементы управления, чтобы установить нужный порядок табуляции.

   > [!NOTE]
   > В качестве места элемента управления в последовательности табуляции можно задать любое значение, большее или равное 0. При возникновении дубликатов вычисляется z-порядок двух элементов управления, а сначала элемент управления на вкладке сверху. (Z-порядок — это визуальное расположение элементов управления в форме вдоль оси z формы [depth]. Z-порядок определяет, какие элементы управления находятся перед другими элементами управления.) Дополнительные сведения о z-порядке см. [в разделе слоевые объекты на Windows Forms](how-to-layer-objects-on-windows-forms.md).

3. По завершении выберите в меню **вид** пункт **последовательность табуляции** , чтобы выйти из режима последовательности табуляции.

   > [!NOTE]
   > Элементы управления, которые не могут получить фокус, а также отключенные и невидимые элементы управления, не имеют <xref:System.Windows.Forms.Control.TabIndex%2A> Свойства и не включаются в последовательность табуляции. Когда пользователь нажимает клавишу TAB, эти элементы управления пропускаются.

Кроме того, можно задать порядок табуляции в окно свойств с помощью <xref:System.Windows.Forms.Control.TabIndex%2A> Свойства. <xref:System.Windows.Forms.Control.TabIndex%2A>Свойство элемента управления определяет, где оно находится в последовательности табуляции. По умолчанию Первый рисуемый элемент управления имеет <xref:System.Windows.Forms.Control.TabIndex%2A> значение 0, второй — <xref:System.Windows.Forms.Control.TabIndex%2A> 1 и т. д.

Кроме того, по умолчанию <xref:System.Windows.Forms.GroupBox> элемент управления имеет собственное <xref:System.Windows.Forms.Control.TabIndex%2A> значение, которое является целым числом. <xref:System.Windows.Forms.GroupBox>Сам элемент управления не может иметь фокус во время выполнения. Таким словами, каждый элемент управления в <xref:System.Windows.Forms.GroupBox> имеет собственное десятичное <xref:System.Windows.Forms.Control.TabIndex%2A> значение, начиная с. 0. Естественно, по мере <xref:System.Windows.Forms.Control.TabIndex%2A> <xref:System.Windows.Forms.GroupBox> увеличения элемента управления элементы управления внутри него будут соответственно увеличены. Если изменить <xref:System.Windows.Forms.Control.TabIndex%2A> значение с 5 на 6, <xref:System.Windows.Forms.Control.TabIndex%2A> значение первого элемента управления в группе автоматически изменится на 6,0 и т. д.

Наконец, любой элемент управления множества в форме можно пропустить в последовательности табуляции. Как правило, при последовательном нажатии клавиши Tab во время выполнения выбирается каждый элемент управления в последовательности табуляции. Отключив <xref:System.Windows.Forms.Control.TabStop%2A> свойство, можно сделать элемент управления передаваться в порядке табуляции в форме.

## <a name="to-remove-a-control-from-the-tab-order"></a>Удаление элемента управления из последовательности табуляции

Присвойте <xref:System.Windows.Forms.Control.TabStop%2A> свойству элемента управления **значение false** в окне **Свойства** .

Элемент управления, <xref:System.Windows.Forms.Control.TabStop%2A> свойство которого имеет значение `false` по-прежнему сохраняет свое расположение в последовательности табуляции, даже если элемент управления пропускается при переходе по элементам управления с помощью клавиши TAB.

> [!NOTE]
> Группа переключателей содержит одну позицию табуляции во время выполнения. Для выбранной кнопки (т. е. для кнопки со <xref:System.Windows.Forms.RadioButton.Checked%2A> свойством, для которой задано значение `true` ) <xref:System.Windows.Forms.Control.TabStop%2A> свойство автоматически устанавливается в значение `true` , а для других кнопок <xref:System.Windows.Forms.Control.TabStop%2A> свойство имеет значение `false` . Дополнительные сведения о группировании <xref:System.Windows.Forms.RadioButton> элементов управления см. [в разделе группирование Windows Forms элементов управления RadioButton для функционирования в виде набора](how-to-group-windows-forms-radiobutton-controls-to-function-as-a-set.md).

## <a name="see-also"></a>См. также раздел

- [Элементы управления Windows Forms](index.md)
- [Элементы управления для использования в формах Windows Forms](controls-to-use-on-windows-forms.md)
- [Функциональная классификация элементов управления Windows Forms](windows-forms-controls-by-function.md)
