---
title: Практическое руководство. Загрузка изображения с помощью конструктора
description: Сведения об использовании элемента управления Windows Forms PictureBox для загрузки и отображения изображения в форме во время разработки.
ms.date: 03/30/2017
helpviewer_keywords:
- picture formats
- images [Windows Forms], displaying on Windows Forms
- pictures [Windows Forms], displaying
- forms [Windows Forms], displaying images
- PictureBox control [Windows Forms], adding pictures
ms.assetid: 4dc7b973-afb1-4276-8322-20825af96655
ms.openlocfilehash: a05ffe19412fc7a4e3e02f01336d89cce39fac8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325602"
---
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a>Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)

С помощью <xref:System.Windows.Forms.PictureBox> элемента управления Windows Forms можно загружать и отображать изображение в форме во время разработки, присвоив <xref:System.Windows.Forms.PictureBox.Image%2A> свойству допустимое изображение. В следующей таблице приведены допустимые типы файлов.

|Type|Расширение имени файла|
|---|---|
|Bitmap|BMP|
|Значок|ICO|
|GIF|.gif|
|Метафайл|. WMF|
|JPEG|.jpg|

## <a name="to-display-a-picture-at-design-time"></a>Отображение рисунка во время разработки

1. Рисование <xref:System.Windows.Forms.PictureBox> элемента управления в форме.

2. В окне **Свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство, а затем нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Открытие** .

3. Если вы ищете конкретный тип файла (например, GIF-файлы), выберите его в поле **файлы типа** .

4. Выберите файл, который требуется отобразить.

## <a name="to-clear-the-picture-at-design-time"></a>Очистка рисунка во время разработки

1. В окне **Свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство. Щелкните правой кнопкой мыши маленький эскиз изображения, который отображается слева от имени объекта Image, и выберите команду **сбросить**.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Forms.PictureBox>
- [Общие сведения об элементе управления PictureBox](picturebox-control-overview-windows-forms.md)
- [Практическое руководство. Изменение размера или размещения изображения во время выполнения](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [Практическое руководство. Установка изображений во время выполнения](how-to-set-pictures-at-run-time-windows-forms.md)
- [Элемент управления PictureBox](picturebox-control-windows-forms.md)
