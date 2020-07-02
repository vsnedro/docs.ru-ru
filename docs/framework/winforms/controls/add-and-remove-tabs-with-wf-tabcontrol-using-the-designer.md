---
title: Добавление и удаление вкладок с помощью элемента TabControl в конструкторе
description: Узнайте, как добавлять и удалять вкладки с Windows Forms элементом управления TabControl с помощью конструктора.
ms.date: 03/30/2017
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabPage control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 480633db-413a-45d2-9c8f-0427cc13adbe
ms.openlocfilehash: 955a671693243ab212180046bb60241c8113a854
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622878"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol-using-the-designer"></a><span data-ttu-id="7d3cf-103">Практическое руководство. Добавление и удаление вкладок с использованием элемента управления TabControl в формах Windows Forms с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="7d3cf-103">How to: Add and Remove Tabs with the Windows Forms TabControl Using the Designer</span></span>
<span data-ttu-id="7d3cf-104">При помещении <xref:System.Windows.Forms.TabControl> элемента управления в форму он по умолчанию содержит две вкладки.</span><span class="sxs-lookup"><span data-stu-id="7d3cf-104">When you place a <xref:System.Windows.Forms.TabControl> control on your form, it contains two tabs by default.</span></span> <span data-ttu-id="7d3cf-105">Можно добавлять или удалять вкладки с помощью конструктора.</span><span class="sxs-lookup"><span data-stu-id="7d3cf-105">You can add or remove tabs using the designer.</span></span>

 <span data-ttu-id="7d3cf-106">Для следующей процедуры требуется проект **приложения Windows** с формой, содержащей <xref:System.Windows.Forms.TabControl> элемент управления.</span><span class="sxs-lookup"><span data-stu-id="7d3cf-106">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.TabControl> control.</span></span> <span data-ttu-id="7d3cf-107">Сведения о настройке такого проекта см. в статьях [как создать проект приложения Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) и [как добавить элементы управления в Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="7d3cf-107">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-or-remove-a-tab-using-the-designer"></a><span data-ttu-id="7d3cf-108">Добавление или удаление вкладки с помощью конструктора</span><span class="sxs-lookup"><span data-stu-id="7d3cf-108">To add or remove a tab using the designer</span></span>

- <span data-ttu-id="7d3cf-109">На смарт-теге элемента управления щелкните **Добавить** вкладку или **Удалить вкладку** .</span><span class="sxs-lookup"><span data-stu-id="7d3cf-109">On the control's smart tag, click **Add Tab** or **Remove Tab**</span></span>

     <span data-ttu-id="7d3cf-110">-или-</span><span class="sxs-lookup"><span data-stu-id="7d3cf-110">-or-</span></span>

     <span data-ttu-id="7d3cf-111">В окне **Свойства** нажмите кнопку **с многоточием** ( ![ кнопку с многоточием (...) в окно свойств Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) рядом со <xref:System.Windows.Forms.TabControl.TabPages%2A> свойством, чтобы открыть **Редактор коллекции TabPage**.</span><span class="sxs-lookup"><span data-stu-id="7d3cf-111">In the **Properties** window, click the **Ellipsis** button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.TabControl.TabPages%2A> property to open the **TabPage Collection Editor**.</span></span> <span data-ttu-id="7d3cf-112">Нажмите кнопку **Добавить** или **Удалить** .</span><span class="sxs-lookup"><span data-stu-id="7d3cf-112">Click the **Add** or **Remove** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d3cf-113">См. также</span><span class="sxs-lookup"><span data-stu-id="7d3cf-113">See also</span></span>

- [<span data-ttu-id="7d3cf-114">Элемент управления TabControl</span><span class="sxs-lookup"><span data-stu-id="7d3cf-114">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="7d3cf-115">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="7d3cf-115">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="7d3cf-116">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="7d3cf-116">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="7d3cf-117">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="7d3cf-117">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="7d3cf-118">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7d3cf-118">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
