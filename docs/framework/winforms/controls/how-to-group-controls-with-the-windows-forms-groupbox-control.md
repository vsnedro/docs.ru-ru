---
title: Группирование элементов управления с помощью элемента управления GroupBox
description: Узнайте, как группировать элементы управления с помощью элемента управления Windows Forms GroupBox, чтобы можно было создать визуальное группирование связанных элементов.
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: f84c495a18f4ae5e04367f024a1e2849f1ed59f9
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618068"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="53c4c-103">Практическое руководство. Группировка элементов управления с помощью элемента управления GroupBox в формах Windows Forms</span><span class="sxs-lookup"><span data-stu-id="53c4c-103">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="53c4c-104"><xref:System.Windows.Forms.GroupBox>Элементы управления Windows Forms используются для группирования других элементов управления.</span><span class="sxs-lookup"><span data-stu-id="53c4c-104">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="53c4c-105">Существуют три причины группировки элементов управления.</span><span class="sxs-lookup"><span data-stu-id="53c4c-105">There are three reasons to group controls:</span></span>  
  
- <span data-ttu-id="53c4c-106">Для создания визуального группирования связанных элементов формы для простого пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="53c4c-106">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
- <span data-ttu-id="53c4c-107">Для создания программного группирования (например, для переключателей).</span><span class="sxs-lookup"><span data-stu-id="53c4c-107">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
- <span data-ttu-id="53c4c-108">Для перемещения элементов управления как единицы во время разработки.</span><span class="sxs-lookup"><span data-stu-id="53c4c-108">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="53c4c-109">Создание группы элементов управления</span><span class="sxs-lookup"><span data-stu-id="53c4c-109">To create a group of controls</span></span>  
  
1. <span data-ttu-id="53c4c-110">Рисование <xref:System.Windows.Forms.GroupBox> элемента управления в форме.</span><span class="sxs-lookup"><span data-stu-id="53c4c-110">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="53c4c-111">Добавьте в поле группы другие элементы управления, нарисовав их внутри поля группы.</span><span class="sxs-lookup"><span data-stu-id="53c4c-111">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="53c4c-112">При наличии существующих элементов управления, которые необходимо заключать в поле группы, можно выбрать все элементы управления, вырезать их в буфер обмена, выбрать <xref:System.Windows.Forms.GroupBox> элемент управления и вставить их в поле Группа.</span><span class="sxs-lookup"><span data-stu-id="53c4c-112">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="53c4c-113">Их также можно перетащить в поле Группа.</span><span class="sxs-lookup"><span data-stu-id="53c4c-113">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="53c4c-114">Задайте <xref:System.Windows.Forms.GroupBox.Text%2A> для свойства поля Группа соответствующий заголовок.</span><span class="sxs-lookup"><span data-stu-id="53c4c-114">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c4c-115">См. также</span><span class="sxs-lookup"><span data-stu-id="53c4c-115">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="53c4c-116">Элемент управления GroupBox</span><span class="sxs-lookup"><span data-stu-id="53c4c-116">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
