---
title: Практическое руководство. Отображение времени с помощью элемента управления DateTimePicker
description: Сведения об использовании элемента управления Windows Forms DateTimePicker для предоставления пользователям возможности выбора даты и времени, а также для отображения даты и времени в указанном формате.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time [Windows Forms], displaying in DateTimePicker control
- examples [Windows Forms], DateTimePicker control
- DateTimePicker control [Windows Forms], displaying time
ms.assetid: 0c1c8b40-1b50-4301-a90c-39516775ccb1
ms.openlocfilehash: ab584367a189d05e567bb57d386c6bf629201102
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325580"
---
# <a name="how-to-display-time-with-the-datetimepicker-control"></a><span data-ttu-id="e7300-103">Практическое руководство. Отображение времени с помощью элемента управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="e7300-103">How to: Display Time with the DateTimePicker Control</span></span>
<span data-ttu-id="e7300-104">Чтобы пользователи приложения могли выбирать дату и время, которые будут отображаться в указанном формате, используйте элемент управления <xref:System.Windows.Forms.DateTimePicker>.</span><span class="sxs-lookup"><span data-stu-id="e7300-104">If you want your application to enable users to select a date and time, and to display that date and time in the specified format, use the <xref:System.Windows.Forms.DateTimePicker> control.</span></span> <span data-ttu-id="e7300-105">Ниже показано, как использовать элемент управления <xref:System.Windows.Forms.DateTimePicker> для отображения времени.</span><span class="sxs-lookup"><span data-stu-id="e7300-105">The following procedure shows how to use the <xref:System.Windows.Forms.DateTimePicker> control to display the time.</span></span>  
  
### <a name="to-display-the-time-with-the-datetimepicker-control"></a><span data-ttu-id="e7300-106">Отображение времени с помощью элемента управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="e7300-106">To display the time with the DateTimePicker control</span></span>  
  
1. <span data-ttu-id="e7300-107">Задайте свойству <xref:System.Windows.Forms.DateTimePicker.Format%2A> значение <xref:System.Windows.Forms.DateTimePickerFormat.Time></span><span class="sxs-lookup"><span data-stu-id="e7300-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to <xref:System.Windows.Forms.DateTimePickerFormat.Time></span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#2)]  
  
2. <span data-ttu-id="e7300-108">Присвойте свойству <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> элемента <xref:System.Windows.Forms.DateTimePicker> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e7300-108">Set the <xref:System.Windows.Forms.DateTimePicker.ShowUpDown%2A> property for the <xref:System.Windows.Forms.DateTimePicker> to `true`.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="e7300-109">Пример</span><span class="sxs-lookup"><span data-stu-id="e7300-109">Example</span></span>  
 <span data-ttu-id="e7300-110">В примере кода ниже показано, как создать элемент <xref:System.Windows.Forms.DateTimePicker>, позволяющий пользователю выбирать только время.</span><span class="sxs-lookup"><span data-stu-id="e7300-110">The following code sample shows how to create a <xref:System.Windows.Forms.DateTimePicker> that enables users to choose a time only.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.DateTimePickerTimeOnly#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DateTimePickerTimeOnly/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e7300-111">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="e7300-111">Compiling the Code</span></span>  
 <span data-ttu-id="e7300-112">Для этого примера требуются:</span><span class="sxs-lookup"><span data-stu-id="e7300-112">This example requires:</span></span>  
  
- <span data-ttu-id="e7300-113">ссылки на сборки System, System.Data, System.Drawing и System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="e7300-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7300-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e7300-114">See also</span></span>

- [<span data-ttu-id="e7300-115">Элемент управления DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="e7300-115">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
