---
title: Просмотр нескольких строк в элементе управления TextBox
description: Узнайте, как просмотреть несколько строк в элементе управления TextBox Windows Forms, установив свойства Multiline, WordWrap и ScrollBars.
ms.date: 03/30/2017
helpviewer_keywords:
- newline
- end of line
- ScrollBars property [Windows Forms], in TextBox control
- CRLF
- MultiLine property in TextBox control
- line-feed
- TextBox control [Windows Forms], viewing multiple lines
- carriage return
ms.assetid: 43173201-0b74-4067-a472-605029ca5f35
ms.openlocfilehash: e40d720bcd56366f4f06bfe2e2d347aaf9aa9d6c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174475"
---
# <a name="how-to-view-multiple-lines-in-the-windows-forms-textbox-control"></a><span data-ttu-id="bc077-103">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc077-103">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>
<span data-ttu-id="bc077-104">По умолчанию <xref:System.Windows.Forms.TextBox> элемент управления Windows Forms отображает одну строку текста и не отображает полосы прокрутки.</span><span class="sxs-lookup"><span data-stu-id="bc077-104">By default, the Windows Forms <xref:System.Windows.Forms.TextBox> control displays a single line of text and does not display scroll bars.</span></span> <span data-ttu-id="bc077-105">Если текст превышает доступное пространство, отображается только часть текста.</span><span class="sxs-lookup"><span data-stu-id="bc077-105">If the text is longer than the available space, only part of the text is visible.</span></span> <span data-ttu-id="bc077-106">Это поведение по умолчанию можно изменить, задав <xref:System.Windows.Forms.TextBox.Multiline%2A> <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> <xref:System.Windows.Forms.TextBox.ScrollBars%2A> для свойств, и соответствующие значения.</span><span class="sxs-lookup"><span data-stu-id="bc077-106">You can change this default behavior by setting the <xref:System.Windows.Forms.TextBox.Multiline%2A>, <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A>, and <xref:System.Windows.Forms.TextBox.ScrollBars%2A> properties to appropriate values.</span></span>  
  
### <a name="to-display-a-carriage-return-in-the-textbox-control"></a><span data-ttu-id="bc077-107">Отображение возврата каретки в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="bc077-107">To display a carriage return in the TextBox control</span></span>  
  
- <span data-ttu-id="bc077-108">Чтобы отобразить возврат каретки в многострочном коде <xref:System.Windows.Forms.TextBox> , используйте <xref:System.Environment.NewLine%2A> свойство.</span><span class="sxs-lookup"><span data-stu-id="bc077-108">To display a carriage return in a multi-line <xref:System.Windows.Forms.TextBox>, use the <xref:System.Environment.NewLine%2A> property.</span></span>  
  
     <span data-ttu-id="bc077-109">Имейте в виду, что интерпретация escape-символов ( \\ ) зависит от языка.</span><span class="sxs-lookup"><span data-stu-id="bc077-109">Be aware that the interpretation of escape characters (\\) is language-specific.</span></span> <span data-ttu-id="bc077-110">Visual Basic использует `Chr$(13) & Chr$(10)` для сочетания символов возврата каретки и перевода строки.</span><span class="sxs-lookup"><span data-stu-id="bc077-110">Visual Basic uses `Chr$(13) & Chr$(10)` for the carriage return and linefeed character combination.</span></span>  
  
### <a name="to-view-multiple-lines-in-the-textbox-control"></a><span data-ttu-id="bc077-111">Просмотр нескольких строк в элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="bc077-111">To view multiple lines in the TextBox control</span></span>  
  
1. <span data-ttu-id="bc077-112">Задайте для свойства <xref:System.Windows.Forms.TextBox.Multiline%2A> значение `true`.</span><span class="sxs-lookup"><span data-stu-id="bc077-112">Set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`.</span></span> <span data-ttu-id="bc077-113">Если <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> имеет значение `true` (по умолчанию), то текст в элементе управления будет отображаться как один или несколько абзацев; в противном случае он будет отображаться в виде списка, в котором некоторые строки могут быть обрезаны по границе элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bc077-113">If <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> is `true` (the default), then the text in the control will appear as one or more paragraphs; otherwise it will appear as a list, in which some lines may be clipped at the edge of the control.</span></span>  
  
2. <span data-ttu-id="bc077-114">Присвойте свойству <xref:System.Windows.Forms.TextBox.ScrollBars%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="bc077-114">Set the <xref:System.Windows.Forms.TextBox.ScrollBars%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="bc077-115">Значение</span><span class="sxs-lookup"><span data-stu-id="bc077-115">Value</span></span>|<span data-ttu-id="bc077-116">Описание</span><span class="sxs-lookup"><span data-stu-id="bc077-116">Description</span></span>|  
    |-----------|-----------------|  
    |<xref:System.Windows.Forms.ScrollBars.None>|<span data-ttu-id="bc077-117">Используйте это значение, если текст будет абзацем, который почти всегда соответствует элементу управления.</span><span class="sxs-lookup"><span data-stu-id="bc077-117">Use this value if the text will be a paragraph that almost always fits the control.</span></span> <span data-ttu-id="bc077-118">Пользователь может использовать указатель мыши для перемещения внутри элемента управления, если текст слишком длинный, чтобы отобразить все одновременно.</span><span class="sxs-lookup"><span data-stu-id="bc077-118">The user can use the mouse pointer to move around inside the control if the text is too long to display all at once.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Horizontal>|<span data-ttu-id="bc077-119">Используйте это значение, если требуется отобразить список строк, некоторые из которых могут быть длиннее ширины <xref:System.Windows.Forms.TextBox> элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bc077-119">Use this value if you want to display a list of lines, some of which may be longer than the width of the <xref:System.Windows.Forms.TextBox> control.</span></span>|  
    |<xref:System.Windows.Forms.ScrollBars.Both>|<span data-ttu-id="bc077-120">Используйте это значение, если список может быть длиннее, чем высота элемента управления.</span><span class="sxs-lookup"><span data-stu-id="bc077-120">Use this value if the list may be longer than the height of the control.</span></span>|  
  
3. <span data-ttu-id="bc077-121">Присвойте свойству <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="bc077-121">Set the <xref:System.Windows.Forms.TextBoxBase.WordWrap%2A> property to an appropriate value.</span></span>  
  
    |<span data-ttu-id="bc077-122">Значение</span><span class="sxs-lookup"><span data-stu-id="bc077-122">Value</span></span>|<span data-ttu-id="bc077-123">Описание</span><span class="sxs-lookup"><span data-stu-id="bc077-123">Description</span></span>|  
    |-----------|-----------------|  
    |`false`|<span data-ttu-id="bc077-124">Текст в элементе управления не будет автоматически заключаться в оболочку, поэтому он будет прокручиваться вправо до тех пор, пока не будет достигнут разрыв строки.</span><span class="sxs-lookup"><span data-stu-id="bc077-124">Text in the control will not automatically be wrapped, so it will scroll to the right until a line break is reached.</span></span> <span data-ttu-id="bc077-125">Используйте это значение, если выбраны <xref:System.Windows.Forms.ScrollBars.Horizontal> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.Both> выше.</span><span class="sxs-lookup"><span data-stu-id="bc077-125">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Horizontal> scroll bars or <xref:System.Windows.Forms.ScrollBars.Both>, above.</span></span>|  
    |<span data-ttu-id="bc077-126">`true` (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="bc077-126">`true` (default)</span></span>|<span data-ttu-id="bc077-127">Горизонтальная полоса прокрутки не будет отображаться.</span><span class="sxs-lookup"><span data-stu-id="bc077-127">The horizontal scrollbar will not appear.</span></span> <span data-ttu-id="bc077-128">Используйте это значение, если вы выбрали <xref:System.Windows.Forms.ScrollBars.Vertical> полосы прокрутки или <xref:System.Windows.Forms.ScrollBars.None> выше, чтобы отобразить один или несколько абзацев.</span><span class="sxs-lookup"><span data-stu-id="bc077-128">Use this value if you chose <xref:System.Windows.Forms.ScrollBars.Vertical> scroll bars or <xref:System.Windows.Forms.ScrollBars.None>, above, to display one or more paragraphs.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bc077-129">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bc077-129">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="bc077-130">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="bc077-130">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="bc077-131">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc077-131">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="bc077-132">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc077-132">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="bc077-133">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="bc077-133">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="bc077-134">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="bc077-134">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="bc077-135">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bc077-135">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="bc077-136">Элемент управления TextBox</span><span class="sxs-lookup"><span data-stu-id="bc077-136">TextBox Control</span></span>](textbox-control-windows-forms.md)
