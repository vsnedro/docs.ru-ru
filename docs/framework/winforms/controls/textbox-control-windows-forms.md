---
title: Элемент управления TextBox
description: Узнайте о различных аспектах элемента управления TextBox Windows Forms, включая его использование для редактируемого текста и делая его доступным только для чтения.
ms.date: 03/30/2017
helpviewer_keywords:
- text boxes
- TextBox control [Windows Forms]
ms.assetid: e5a06987-8aec-4271-b196-2245ba992d62
ms.openlocfilehash: 026f6d2653e41dabd3db7490660b6ce19846d397
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174449"
---
# <a name="textbox-control-windows-forms"></a><span data-ttu-id="7f35f-103">Элемент управления TextBox (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="7f35f-103">TextBox Control (Windows Forms)</span></span>
<span data-ttu-id="7f35f-104">Windows Forms текстовые поля используются для получения входных данных от пользователя или для вывода текста.</span><span class="sxs-lookup"><span data-stu-id="7f35f-104">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="7f35f-105">`TextBox`Элемент управления обычно используется для редактируемого текста, хотя его также можно сделать доступным только для чтения.</span><span class="sxs-lookup"><span data-stu-id="7f35f-105">The `TextBox` control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="7f35f-106">Текстовые поля могут отображать несколько строк, переносить текст в размер элемента управления и добавлять базовое форматирование.</span><span class="sxs-lookup"><span data-stu-id="7f35f-106">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="7f35f-107">`TextBox`Элемент управления допускает один формат текста, отображаемого или вводимых в элементе управления.</span><span class="sxs-lookup"><span data-stu-id="7f35f-107">The `TextBox` control allows a single format for text displayed or entered in the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7f35f-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="7f35f-108">In This Section</span></span>  
 [<span data-ttu-id="7f35f-109">Общие сведения об элементе управления TextBox</span><span class="sxs-lookup"><span data-stu-id="7f35f-109">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)  
 <span data-ttu-id="7f35f-110">Описание элемента управления, его основных возможностей и свойств.</span><span class="sxs-lookup"><span data-stu-id="7f35f-110">Explains what this control is and its key features and properties.</span></span>  
  
 [<span data-ttu-id="7f35f-111">Практическое руководство. Управление положением курсора в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f35f-111">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)  
 <span data-ttu-id="7f35f-112">Инструкции по указанию места, где точка вставки появляется при первом получении фокуса элементом управления "поле ввода".</span><span class="sxs-lookup"><span data-stu-id="7f35f-112">Gives directions for specifying where the insertion point appears when an edit control first gets the focus.</span></span>  
  
 [<span data-ttu-id="7f35f-113">Практическое руководство. Создание текстового поля для ввода пароля с помощью элемента управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f35f-113">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="7f35f-114">Объясняет, как скрыть текст, вводимый в текстовое поле.</span><span class="sxs-lookup"><span data-stu-id="7f35f-114">Explains how to conceal what is typed into a text box.</span></span>  
  
 [<span data-ttu-id="7f35f-115">Практическое руководство. Создание текстового поля только для чтения</span><span class="sxs-lookup"><span data-stu-id="7f35f-115">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)  
 <span data-ttu-id="7f35f-116">Описывает, как предотвратить изменение содержимого текстового поля.</span><span class="sxs-lookup"><span data-stu-id="7f35f-116">Describes how to prevent the contents of a text box from being changed.</span></span>  
  
 [<span data-ttu-id="7f35f-117">Практическое руководство. Добавление кавычек в строку</span><span class="sxs-lookup"><span data-stu-id="7f35f-117">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)  
 <span data-ttu-id="7f35f-118">Описание добавления кавычек к строке в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="7f35f-118">Explains adding quotation marks to a string in a text box.</span></span>  
  
 [<span data-ttu-id="7f35f-119">Практическое руководство. Выделение текста в элементе управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f35f-119">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="7f35f-120">Объясняет, как выделить текст в текстовом поле.</span><span class="sxs-lookup"><span data-stu-id="7f35f-120">Explains how to highlight text in a text box.</span></span>  
  
 [<span data-ttu-id="7f35f-121">Практическое руководство. Многострочные элементы управления TextBox в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f35f-121">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)  
 <span data-ttu-id="7f35f-122">Описывает, как сделать текстовое поле прокручиваемым.</span><span class="sxs-lookup"><span data-stu-id="7f35f-122">Describes how to make a text box scrollable.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="7f35f-123">Ссылка</span><span class="sxs-lookup"><span data-stu-id="7f35f-123">Reference</span></span>  
 <span data-ttu-id="7f35f-124">Класс <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="7f35f-124"><xref:System.Windows.Forms.TextBox> class</span></span>  
 <span data-ttu-id="7f35f-125">Описание класса и всех его членов.</span><span class="sxs-lookup"><span data-stu-id="7f35f-125">Describes this class and has links to all its members.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7f35f-126">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="7f35f-126">Related Sections</span></span>  
 [<span data-ttu-id="7f35f-127">Элементы управления для использования в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7f35f-127">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)  
 <span data-ttu-id="7f35f-128">Полный список элементов управления Windows Forms со ссылками на информацию об их применении.</span><span class="sxs-lookup"><span data-stu-id="7f35f-128">Provides a complete list of Windows Forms controls, with links to information on their use.</span></span>
