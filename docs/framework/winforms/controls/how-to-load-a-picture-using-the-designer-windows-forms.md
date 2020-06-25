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
# <a name="how-to-load-a-picture-using-the-designer-windows-forms"></a><span data-ttu-id="736ef-103">Практическое руководство. Загрузка изображения с помощью конструктора (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="736ef-103">How to: Load a Picture Using the Designer (Windows Forms)</span></span>

<span data-ttu-id="736ef-104">С помощью <xref:System.Windows.Forms.PictureBox> элемента управления Windows Forms можно загружать и отображать изображение в форме во время разработки, присвоив <xref:System.Windows.Forms.PictureBox.Image%2A> свойству допустимое изображение.</span><span class="sxs-lookup"><span data-stu-id="736ef-104">With the Windows Forms <xref:System.Windows.Forms.PictureBox> control, you can load and display a picture on a form at design time by setting the <xref:System.Windows.Forms.PictureBox.Image%2A> property to a valid picture.</span></span> <span data-ttu-id="736ef-105">В следующей таблице приведены допустимые типы файлов.</span><span class="sxs-lookup"><span data-stu-id="736ef-105">The following table shows the acceptable file types.</span></span>

|<span data-ttu-id="736ef-106">Type</span><span class="sxs-lookup"><span data-stu-id="736ef-106">Type</span></span>|<span data-ttu-id="736ef-107">Расширение имени файла</span><span class="sxs-lookup"><span data-stu-id="736ef-107">File name extension</span></span>|
|---|---|
|<span data-ttu-id="736ef-108">Bitmap</span><span class="sxs-lookup"><span data-stu-id="736ef-108">Bitmap</span></span>|<span data-ttu-id="736ef-109">BMP</span><span class="sxs-lookup"><span data-stu-id="736ef-109">.bmp</span></span>|
|<span data-ttu-id="736ef-110">Значок</span><span class="sxs-lookup"><span data-stu-id="736ef-110">Icon</span></span>|<span data-ttu-id="736ef-111">ICO</span><span class="sxs-lookup"><span data-stu-id="736ef-111">.ico</span></span>|
|<span data-ttu-id="736ef-112">GIF</span><span class="sxs-lookup"><span data-stu-id="736ef-112">GIF</span></span>|<span data-ttu-id="736ef-113">.gif</span><span class="sxs-lookup"><span data-stu-id="736ef-113">.gif</span></span>|
|<span data-ttu-id="736ef-114">Метафайл</span><span class="sxs-lookup"><span data-stu-id="736ef-114">Metafile</span></span>|<span data-ttu-id="736ef-115">. WMF</span><span class="sxs-lookup"><span data-stu-id="736ef-115">.wmf</span></span>|
|<span data-ttu-id="736ef-116">JPEG</span><span class="sxs-lookup"><span data-stu-id="736ef-116">JPEG</span></span>|<span data-ttu-id="736ef-117">.jpg</span><span class="sxs-lookup"><span data-stu-id="736ef-117">.jpg</span></span>|

## <a name="to-display-a-picture-at-design-time"></a><span data-ttu-id="736ef-118">Отображение рисунка во время разработки</span><span class="sxs-lookup"><span data-stu-id="736ef-118">To display a picture at design time</span></span>

1. <span data-ttu-id="736ef-119">Рисование <xref:System.Windows.Forms.PictureBox> элемента управления в форме.</span><span class="sxs-lookup"><span data-stu-id="736ef-119">Draw a <xref:System.Windows.Forms.PictureBox> control on a form.</span></span>

2. <span data-ttu-id="736ef-120">В окне **Свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство, а затем нажмите кнопку с многоточием, чтобы открыть диалоговое окно **Открытие** .</span><span class="sxs-lookup"><span data-stu-id="736ef-120">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property, then select the ellipsis button to display the **Open** dialog box.</span></span>

3. <span data-ttu-id="736ef-121">Если вы ищете конкретный тип файла (например, GIF-файлы), выберите его в поле **файлы типа** .</span><span class="sxs-lookup"><span data-stu-id="736ef-121">If you're looking for a specific file type (for example, .gif files), select it in the **Files of type** box.</span></span>

4. <span data-ttu-id="736ef-122">Выберите файл, который требуется отобразить.</span><span class="sxs-lookup"><span data-stu-id="736ef-122">Select the file you want to display.</span></span>

## <a name="to-clear-the-picture-at-design-time"></a><span data-ttu-id="736ef-123">Очистка рисунка во время разработки</span><span class="sxs-lookup"><span data-stu-id="736ef-123">To clear the picture at design time</span></span>

1. <span data-ttu-id="736ef-124">В окне **Свойства** выберите <xref:System.Windows.Forms.PictureBox.Image%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="736ef-124">In the **Properties** window, select the <xref:System.Windows.Forms.PictureBox.Image%2A> property.</span></span> <span data-ttu-id="736ef-125">Щелкните правой кнопкой мыши маленький эскиз изображения, который отображается слева от имени объекта Image, и выберите команду **сбросить**.</span><span class="sxs-lookup"><span data-stu-id="736ef-125">Right-click the small thumbnail image that appears to the left of the name of the image object, and then choose **Reset**.</span></span>

## <a name="see-also"></a><span data-ttu-id="736ef-126">См. также</span><span class="sxs-lookup"><span data-stu-id="736ef-126">See also</span></span>

- <xref:System.Windows.Forms.PictureBox>
- [<span data-ttu-id="736ef-127">Общие сведения об элементе управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="736ef-127">PictureBox Control Overview</span></span>](picturebox-control-overview-windows-forms.md)
- [<span data-ttu-id="736ef-128">Практическое руководство. Изменение размера или размещения изображения во время выполнения</span><span class="sxs-lookup"><span data-stu-id="736ef-128">How to: Modify the Size or Placement of a Picture at Run Time</span></span>](how-to-modify-the-size-or-placement-of-a-picture-at-run-time-windows-forms.md)
- [<span data-ttu-id="736ef-129">Практическое руководство. Установка изображений во время выполнения</span><span class="sxs-lookup"><span data-stu-id="736ef-129">How to: Set Pictures at Run Time</span></span>](how-to-set-pictures-at-run-time-windows-forms.md)
- [<span data-ttu-id="736ef-130">Элемент управления PictureBox</span><span class="sxs-lookup"><span data-stu-id="736ef-130">PictureBox Control</span></span>](picturebox-control-windows-forms.md)
