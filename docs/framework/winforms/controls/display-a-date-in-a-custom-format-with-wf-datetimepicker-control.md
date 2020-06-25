---
title: Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker
description: Сведения об использовании элемента управления Windows Forms DateTimePicker для форматирования отображения даты и времени в элементе управления.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: 773070136e4fd43ab1bf510ebcaf6b0aa6a7ba8a
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325835"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="1e338-103">Практическое руководство. Отображение даты в пользовательском формате с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e338-103">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="1e338-104"><xref:System.Windows.Forms.DateTimePicker>Элемент управления Windows Forms обеспечивает гибкость при форматировании отображаемых дат и времени в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="1e338-104">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="1e338-105"><xref:System.Windows.Forms.DateTimePicker.Format%2A>Свойство позволяет выбрать из предопределенных форматов, перечисленных в <xref:System.Windows.Forms.DateTimePickerFormat> .</span><span class="sxs-lookup"><span data-stu-id="1e338-105">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="1e338-106">Если ни один из этих средств не подходит для ваших целей, можно создать собственный стиль форматирования, используя символы формата, перечисленные в <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> .</span><span class="sxs-lookup"><span data-stu-id="1e338-106">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="1e338-107">Отображение пользовательского формата</span><span class="sxs-lookup"><span data-stu-id="1e338-107">To display a custom format</span></span>  
  
1. <span data-ttu-id="1e338-108">Задайте для свойства <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="1e338-108">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="1e338-109">Задайте <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> для свойства строку формата.</span><span class="sxs-lookup"><span data-stu-id="1e338-109">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="1e338-110">Добавление текста к отформатированному значению</span><span class="sxs-lookup"><span data-stu-id="1e338-110">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="1e338-111">Используйте одинарные кавычки для заключения любого символа, который не является символом формата, например "M", или разделителя, например ":".</span><span class="sxs-lookup"><span data-stu-id="1e338-111">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="1e338-112">Например, приведенная ниже строка форматирования отображает текущую дату в формате "сегодня: 05:30:31 пятница марта 02, 2012" в английской (США) культуре.</span><span class="sxs-lookup"><span data-stu-id="1e338-112">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="1e338-113">В зависимости от настройки языка и региональных параметров все символы, не заключенные в одинарные кавычки, могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="1e338-113">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="1e338-114">Например, приведенная выше строка форматирования отображает текущую дату в формате "сегодня: 05:30:31 пятница марта 02, 2012" в английской (США) культуре.</span><span class="sxs-lookup"><span data-stu-id="1e338-114">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="1e338-115">Обратите внимание, что первое двоеточие заключено в одинарные кавычки, так как оно не должно быть символом-разделителем, как в «чч: мм: СС».</span><span class="sxs-lookup"><span data-stu-id="1e338-115">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="1e338-116">В другом языке и региональных параметрах формат может выглядеть как "сегодня: 05.30.31 пятница, 02 марта, 2012".</span><span class="sxs-lookup"><span data-stu-id="1e338-116">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e338-117">См. также</span><span class="sxs-lookup"><span data-stu-id="1e338-117">See also</span></span>

- [<span data-ttu-id="1e338-118">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="1e338-118">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="1e338-119">Практическое руководство. Отображение и ввод дат с помощью элемента управления DateTimePicker в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1e338-119">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
