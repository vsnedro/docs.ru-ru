---
title: Практическое руководство. Создание дочерних форм MDI
description: Узнайте, как использовать Visual Studio для создания дочерней формы многодокументного интерфейса (MDI), отображающей элемент управления RichTextBox.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MDI [Windows Forms], creating forms
- child forms
ms.assetid: 164b69bb-2eca-4339-ada3-0679eb2c6dda
ms.openlocfilehash: 7fe5cde342f0f5ee078f888b7492cd4618bea5c4
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903185"
---
# <a name="how-to-create-mdi-child-forms"></a><span data-ttu-id="b47f1-103">Как создавать дочерние формы MDI</span><span class="sxs-lookup"><span data-stu-id="b47f1-103">How to: Create MDI child forms</span></span>

<span data-ttu-id="b47f1-104">Дочерние MDI-формы являются ключевым элементом [приложений с интерфейсом MDI](multiple-document-interface-mdi-applications.md), так как эти формы являются центром взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="b47f1-104">MDI child forms are an essential element of [Multiple-Document Interface (MDI) applications](multiple-document-interface-mdi-applications.md), as these forms are the center of user interaction.</span></span>

<span data-ttu-id="b47f1-105">В следующей процедуре Visual Studio используется для создания дочерней MDI-формы, отображающей <xref:System.Windows.Forms.RichTextBox> элемент управления, аналогично большинству приложений для обработки текстов.</span><span class="sxs-lookup"><span data-stu-id="b47f1-105">In the following procedure, you'll use Visual Studio to create an MDI child form that displays a <xref:System.Windows.Forms.RichTextBox> control, similar to most word-processing applications.</span></span> <span data-ttu-id="b47f1-106">Подставив <xref:System.Windows.Forms> элемент управления другими элементами управления, такими как <xref:System.Windows.Forms.DataGridView> элемент управления или сочетанием элементов управления, можно создавать дочерние MDI-окна (и, по расширениям, приложения MDI) с различными возможностями.</span><span class="sxs-lookup"><span data-stu-id="b47f1-106">By substituting the <xref:System.Windows.Forms> control with other controls, such as the <xref:System.Windows.Forms.DataGridView> control, or a mixture of controls, you can create MDI child windows (and, by extension, MDI applications) with diverse possibilities.</span></span>

## <a name="create-mdi-child-forms"></a><span data-ttu-id="b47f1-107">Создание дочерних форм MDI</span><span class="sxs-lookup"><span data-stu-id="b47f1-107">Create MDI child forms</span></span>

1. <span data-ttu-id="b47f1-108">Создание нового проекта Windows Forms приложения в Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b47f1-108">Create a new Windows Forms application project in Visual Studio.</span></span> <span data-ttu-id="b47f1-109">В окне **свойств** формы установите для свойства значение, а для свойства — значение <xref:System.Windows.Forms.Form.IsMdiContainer%2A> `true` `WindowsState` `Maximized` .</span><span class="sxs-lookup"><span data-stu-id="b47f1-109">In the **Properties** window for the form, set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true` and its `WindowsState` property to `Maximized`.</span></span>

   <span data-ttu-id="b47f1-110">При этом форма назначается в качестве MDI-контейнера для дочерних окон.</span><span class="sxs-lookup"><span data-stu-id="b47f1-110">This designates the form as an MDI container for child windows.</span></span>

2. <span data-ttu-id="b47f1-111">Из `Toolbox` перетащите элемент управления <xref:System.Windows.Forms.MenuStrip> в форму.</span><span class="sxs-lookup"><span data-stu-id="b47f1-111">From the `Toolbox`, drag a <xref:System.Windows.Forms.MenuStrip> control to the form.</span></span> <span data-ttu-id="b47f1-112">Присвойте `Text` свойству значение **File**.</span><span class="sxs-lookup"><span data-stu-id="b47f1-112">Set its `Text` property to **File**.</span></span>

3. <span data-ttu-id="b47f1-113">Нажмите кнопку с многоточием (...) рядом со свойством **Items** и нажмите кнопку **Добавить** , чтобы добавить два дочерних пункта меню.</span><span class="sxs-lookup"><span data-stu-id="b47f1-113">Click the ellipsis (…) next to the **Items** property, and click **Add** to add two child tool strip menu items.</span></span> <span data-ttu-id="b47f1-114">Установите для `Text` этих элементов свойство " **новое** " и " **окно**".</span><span class="sxs-lookup"><span data-stu-id="b47f1-114">Set the `Text` property for these items to **New** and **Window**.</span></span>

4. <span data-ttu-id="b47f1-115">В **обозревателе решений** щелкните проект правой кнопкой мыши и выберите пункты **Добавить** > **Новый элемент**.</span><span class="sxs-lookup"><span data-stu-id="b47f1-115">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

5. <span data-ttu-id="b47f1-116">В диалоговом окне **Добавление нового элемента** выберите **Windows Form** (в Visual Basic или в Visual C#) или **Windows Forms приложение (.NET)** (в Visual C++) в области **шаблоны** .</span><span class="sxs-lookup"><span data-stu-id="b47f1-116">In the **Add New Item** dialog box, select **Windows Form** (in Visual Basic or in Visual C#) or **Windows Forms Application (.NET)** (in Visual C++) from the **Templates** pane.</span></span> <span data-ttu-id="b47f1-117">В поле **имя** введите имя формы **Form2**.</span><span class="sxs-lookup"><span data-stu-id="b47f1-117">In the **Name** box, name the form **Form2**.</span></span> <span data-ttu-id="b47f1-118">Нажмите кнопку **Открыть** , чтобы добавить форму в проект.</span><span class="sxs-lookup"><span data-stu-id="b47f1-118">Select **Open** to add the form to the project.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b47f1-119">Дочерняя форма MDI, созданная на этом этапе, является стандартной формой Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="b47f1-119">The MDI child form you created in this step is a standard Windows Form.</span></span> <span data-ttu-id="b47f1-120">Таким образом, у нее есть свойство <xref:System.Windows.Forms.Form.Opacity%2A>, которое позволяет управлять прозрачностью формы.</span><span class="sxs-lookup"><span data-stu-id="b47f1-120">As such, it has an <xref:System.Windows.Forms.Form.Opacity%2A> property, which enables you to control the transparency of the form.</span></span> <span data-ttu-id="b47f1-121">Однако свойство <xref:System.Windows.Forms.Form.Opacity%2A> предназначено для окон верхнего уровня.</span><span class="sxs-lookup"><span data-stu-id="b47f1-121">However, the <xref:System.Windows.Forms.Form.Opacity%2A> property was designed for top-level windows.</span></span> <span data-ttu-id="b47f1-122">Его не следует использовать в дочерних формах MDI, иначе могут возникнуть проблемы с рисованием.</span><span class="sxs-lookup"><span data-stu-id="b47f1-122">Do not use it with MDI child forms, as painting problems can occur.</span></span>

     <span data-ttu-id="b47f1-123">Эта форма будет шаблоном для дочерних форм MDI.</span><span class="sxs-lookup"><span data-stu-id="b47f1-123">This form will be the template for your MDI child forms.</span></span>

     <span data-ttu-id="b47f1-124">Откроется **конструктор Windows Forms** , отображающий **Form2**.</span><span class="sxs-lookup"><span data-stu-id="b47f1-124">The **Windows Forms Designer** opens, displaying **Form2**.</span></span>

6. <span data-ttu-id="b47f1-125">Перетащите элемент управления **RichTextBox** из **панели элементов**в форму.</span><span class="sxs-lookup"><span data-stu-id="b47f1-125">From the **Toolbox**, drag a **RichTextBox** control to the form.</span></span>

7. <span data-ttu-id="b47f1-126">В окне **Свойства** задайте `Anchor` для свойства значение **сверху, слева** и `Dock` свойство для **заполнения**.</span><span class="sxs-lookup"><span data-stu-id="b47f1-126">In the **Properties** window, set the `Anchor` property to **Top, Left** and the `Dock` property to **Fill**.</span></span>

   <span data-ttu-id="b47f1-127">В результате элемент управления <xref:System.Windows.Forms.RichTextBox> будет целиком заполнять область дочерней формы MDI, даже если ее размеры изменятся.</span><span class="sxs-lookup"><span data-stu-id="b47f1-127">This causes the <xref:System.Windows.Forms.RichTextBox> control to completely fill the area of the MDI child form, even when the form is resized.</span></span>

8. <span data-ttu-id="b47f1-128">Дважды щелкните **Новый** элемент меню, чтобы создать <xref:System.Windows.Forms.Control.Click> для него обработчик событий.</span><span class="sxs-lookup"><span data-stu-id="b47f1-128">Double click the **New** menu item to create a <xref:System.Windows.Forms.Control.Click> event handler for it.</span></span>

9. <span data-ttu-id="b47f1-129">Вставьте код, аналогичный приведенному ниже, чтобы создать новую дочернюю форму MDI, когда пользователь щелкнет **Новый** элемент меню.</span><span class="sxs-lookup"><span data-stu-id="b47f1-129">Insert code similar to the following to create a new MDI child form when the user clicks the **New** menu item.</span></span>

   > [!NOTE]
   > <span data-ttu-id="b47f1-130">В примере ниже обработчик событий обрабатывает событие <xref:System.Windows.Forms.Control.Click> для `MenuItem2`.</span><span class="sxs-lookup"><span data-stu-id="b47f1-130">In the following example, the event handler handles the <xref:System.Windows.Forms.Control.Click> event for `MenuItem2`.</span></span> <span data-ttu-id="b47f1-131">Имейте в виду, что в зависимости от особенностей архитектуры приложения **Новый** пункт меню может не быть `MenuItem2` .</span><span class="sxs-lookup"><span data-stu-id="b47f1-131">Be aware that, depending on the specifics of your application architecture, your **New** menu item may not be `MenuItem2`.</span></span>

    ```vb
    Protected Sub MDIChildNew_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MenuItem2.Click
       Dim NewMDIChild As New Form2()
       'Set the Parent Form of the Child window.
       NewMDIChild.MdiParent = Me
       'Display the new form.
       NewMDIChild.Show()
    End Sub
    ```

    ```csharp
    protected void MDIChildNew_Click(object sender, System.EventArgs e){
       Form2 newMDIChild = new Form2();
       // Set the Parent Form of the Child window.
       newMDIChild.MdiParent = this;
       // Display the new form.
       newMDIChild.Show();
    }
    ```

    ```cpp
    private:
       void menuItem2_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          Form2^ newMDIChild = gcnew Form2();
          // Set the Parent Form of the Child window.
          newMDIChild->MdiParent = this;
          // Display the new form.
          newMDIChild->Show();
       }
    ```

   <span data-ttu-id="b47f1-132">В C++ добавьте следующую `#include` директиву в верхней части Form1. h:</span><span class="sxs-lookup"><span data-stu-id="b47f1-132">In C++, add the following `#include` directive at the top of Form1.h:</span></span>

   ```cpp
   #include "Form2.h"
   ```

10. <span data-ttu-id="b47f1-133">В раскрывающемся списке в верхней части окна **Свойства** выберите полосу меню, соответствующую полосе меню **файл** , и задайте <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> для свойства значение окно <xref:System.Windows.Forms.ToolStripMenuItem> .</span><span class="sxs-lookup"><span data-stu-id="b47f1-133">In the drop-down list at the top of the **Properties** window, select the menu strip that corresponds to the **File** menu strip and set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property to the Window <xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>

    <span data-ttu-id="b47f1-134">Это позволяет меню " **окно** " поддерживать список открытых дочерних окон MDI с галочкой рядом с активным дочерним окном.</span><span class="sxs-lookup"><span data-stu-id="b47f1-134">This enables the **Window** menu to maintain a list of open MDI child windows with a check mark next to the active child window.</span></span>

11. <span data-ttu-id="b47f1-135">Нажмите клавишу **F5** для запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="b47f1-135">Press **F5** to run the application.</span></span> <span data-ttu-id="b47f1-136">Выбрав пункт **создать** в меню **файл** , можно создать дочерние MDI-формы, которые будут храниться в пункте меню **окно** .</span><span class="sxs-lookup"><span data-stu-id="b47f1-136">By selecting **New** from the **File** menu, you can create new MDI child forms, which are kept track of in the **Window** menu item.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b47f1-137">Когда в дочерней форме MDI есть компонент <xref:System.Windows.Forms.MainMenu> (обычно обладающий структурой пунктов меню) и он открыт внутри родительской формы MDI, также имеющей компонент <xref:System.Windows.Forms.MainMenu> (обычно обладающий структурой пунктов меню), пункты меню будут объединены автоматически, если задано свойство <xref:System.Windows.Forms.MenuItem.MergeType%2A> (и, возможно, свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A>).</span><span class="sxs-lookup"><span data-stu-id="b47f1-137">When an MDI child form has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items) and it is opened within an MDI parent form that has a <xref:System.Windows.Forms.MainMenu> component (with, usually, a menu structure of menu items), the menu items will merge automatically if you have set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property (and optionally, the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property).</span></span> <span data-ttu-id="b47f1-138">Установите для свойства <xref:System.Windows.Forms.MenuItem.MergeType%2A> обоих компонентов <xref:System.Windows.Forms.MainMenu> и всех пунктов меню дочерней формы значение <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span><span class="sxs-lookup"><span data-stu-id="b47f1-138">Set the <xref:System.Windows.Forms.MenuItem.MergeType%2A> property of both <xref:System.Windows.Forms.MainMenu> components and all of the menu items of the child form to <xref:System.Windows.Forms.MenuMerge.MergeItems>.</span></span> <span data-ttu-id="b47f1-139">Кроме того, установите свойство <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> таким образом, чтобы пункты обоих меню приводились в нужном порядке.</span><span class="sxs-lookup"><span data-stu-id="b47f1-139">Additionally, set the <xref:System.Windows.Forms.MenuItem.MergeOrder%2A> property so that the menu items from both menus appear in the desired order.</span></span> <span data-ttu-id="b47f1-140">Необходимо помнить, что при закрытии родительской формы MDI каждая из дочерних форм MDI создает событие <xref:System.Windows.Forms.Form.Closing> до создания события <xref:System.Windows.Forms.Form.Closing> для родительской формы MDI.</span><span class="sxs-lookup"><span data-stu-id="b47f1-140">Moreover, keep in mind that when you close an MDI parent form, each of the MDI child forms raises a <xref:System.Windows.Forms.Form.Closing> event before the <xref:System.Windows.Forms.Form.Closing> event for the MDI parent is raised.</span></span> <span data-ttu-id="b47f1-141">Отмена события <xref:System.Windows.Forms.Form.Closing> дочерней формы MDI не отменяет событие <xref:System.Windows.Forms.Form.Closing> родительской формы MDI. Однако для аргумента <xref:System.ComponentModel.CancelEventArgs> для события <xref:System.Windows.Forms.Form.Closing> родительской формы MDI будет установлено значение `true`.</span><span class="sxs-lookup"><span data-stu-id="b47f1-141">Canceling an MDI child's <xref:System.Windows.Forms.Form.Closing> event will not prevent the MDI parent's <xref:System.Windows.Forms.Form.Closing> event from being raised; however, the <xref:System.ComponentModel.CancelEventArgs> argument for the MDI parent's <xref:System.Windows.Forms.Form.Closing> event will now be set to `true`.</span></span> <span data-ttu-id="b47f1-142">Чтобы принудительно закрыть родительскую и все дочерние формы MDI, задайте для аргумента <xref:System.ComponentModel.CancelEventArgs> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b47f1-142">You can force the MDI parent and all MDI child forms to close by setting the <xref:System.ComponentModel.CancelEventArgs> argument to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b47f1-143">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b47f1-143">See also</span></span>

- [<span data-ttu-id="b47f1-144">Приложения с интерфейсом MDI</span><span class="sxs-lookup"><span data-stu-id="b47f1-144">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="b47f1-145">Практическое руководство. Создание родительских MDI-форм</span><span class="sxs-lookup"><span data-stu-id="b47f1-145">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="b47f1-146">Практическое руководство. Определение активной дочерней MDI-формы</span><span class="sxs-lookup"><span data-stu-id="b47f1-146">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="b47f1-147">Практическое руководство. Отправка данных в активную дочернюю MDI-форму</span><span class="sxs-lookup"><span data-stu-id="b47f1-147">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
- [<span data-ttu-id="b47f1-148">Практическое руководство. Упорядочение дочерних MDI-форм</span><span class="sxs-lookup"><span data-stu-id="b47f1-148">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
