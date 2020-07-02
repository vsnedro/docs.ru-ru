---
title: Добавление и удаление вкладок с помощью элемента TabControl
description: Узнайте, как добавлять и удалять вкладки с Windows Forms элементом управления TabControl, который содержит два элемента управления TabPage. Доступ к этим вкладкам осуществляется через свойство Табпажес.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tabs [Windows Forms], removing from pages
- TabPage control
- TabControl control [Windows Forms], adding and removing tabs
- tabs [Windows Forms], adding to pages
- tab pages
ms.assetid: 66d4dfca-41e8-44e3-9c80-fb7ac4cb1619
ms.openlocfilehash: 7e67d0bbc13bd7d9c8835dc6fb9b9c5c9333b8bf
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618081"
---
# <a name="how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol"></a><span data-ttu-id="f6921-104">Практическое руководство. Добавление и удаление вкладок с помощью элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6921-104">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>
<span data-ttu-id="f6921-105">По умолчанию <xref:System.Windows.Forms.TabControl> элемент управления содержит два элемента <xref:System.Windows.Forms.TabPage> управления.</span><span class="sxs-lookup"><span data-stu-id="f6921-105">By default, a <xref:System.Windows.Forms.TabControl> control contains two <xref:System.Windows.Forms.TabPage> controls.</span></span> <span data-ttu-id="f6921-106">Доступ к этим вкладкам можно получить с помощью <xref:System.Windows.Forms.TabControl.TabPages%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="f6921-106">You can access these tabs through the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
### <a name="to-add-a-tab-programmatically"></a><span data-ttu-id="f6921-107">Добавление вкладки программными средствами</span><span class="sxs-lookup"><span data-stu-id="f6921-107">To add a tab programmatically</span></span>  
  
- <span data-ttu-id="f6921-108">Используйте <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> метод <xref:System.Windows.Forms.TabControl.TabPages%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="f6921-108">Use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Add%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    Dim myTabPage As New TabPage()  
    myTabPage.Text = "TabPage" & (TabControl1.TabPages.Count + 1)  
    TabControl1.TabPages.Add(myTabPage)  
    ```  
  
    ```csharp  
    string title = "TabPage " + (tabControl1.TabCount + 1).ToString();  
    TabPage myTabPage = new TabPage(title);  
    tabControl1.TabPages.Add(myTabPage);  
    ```  
  
    ```cpp  
    String^ title = String::Concat("TabPage ",  
       (tabControl1->TabCount + 1).ToString());  
    TabPage^ myTabPage = gcnew TabPage(title);  
    tabControl1->TabPages->Add(myTabPage);  
    ```  
  
### <a name="to-remove-a-tab-programmatically"></a><span data-ttu-id="f6921-109">Удаление вкладки программным способом</span><span class="sxs-lookup"><span data-stu-id="f6921-109">To remove a tab programmatically</span></span>  
  
- <span data-ttu-id="f6921-110">Чтобы удалить выбранные вкладки, используйте <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> метод <xref:System.Windows.Forms.TabControl.TabPages%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="f6921-110">To remove selected tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Remove%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
     <span data-ttu-id="f6921-111">-или-</span><span class="sxs-lookup"><span data-stu-id="f6921-111">-or-</span></span>  
  
- <span data-ttu-id="f6921-112">Чтобы удалить все вкладки, используйте <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> метод <xref:System.Windows.Forms.TabControl.TabPages%2A> Свойства.</span><span class="sxs-lookup"><span data-stu-id="f6921-112">To remove all tabs, use the <xref:System.Windows.Forms.TabControl.TabPageCollection.Clear%2A> method of the <xref:System.Windows.Forms.TabControl.TabPages%2A> property.</span></span>  
  
    ```vb  
    ' Removes the selected tab:  
    TabControl1.TabPages.Remove(TabControl1.SelectedTab)  
    ' Removes all the tabs:  
    TabControl1.TabPages.Clear()  
    ```  
  
    ```csharp  
    // Removes the selected tab:  
    tabControl1.TabPages.Remove(tabControl1.SelectedTab);  
    // Removes all the tabs:  
    tabControl1.TabPages.Clear();  
    ```  
  
    ```cpp  
    // Removes the selected tab:  
    tabControl1->TabPages->Remove(tabControl1->SelectedTab);  
    // Removes all the tabs:  
    tabControl1->TabPages->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f6921-113">См. также</span><span class="sxs-lookup"><span data-stu-id="f6921-113">See also</span></span>

- [<span data-ttu-id="f6921-114">Общие сведения об элементе управления TabControl</span><span class="sxs-lookup"><span data-stu-id="f6921-114">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="f6921-115">Практическое руководство. Добавление элемента управления на вкладку</span><span class="sxs-lookup"><span data-stu-id="f6921-115">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="f6921-116">Практическое руководство. Блокировка доступа ко вкладкам</span><span class="sxs-lookup"><span data-stu-id="f6921-116">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="f6921-117">Практическое руководство. Изменение внешнего вида элемента управления TabControl в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f6921-117">How to: Change the Appearance of the Windows Forms TabControl</span></span>](how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)
