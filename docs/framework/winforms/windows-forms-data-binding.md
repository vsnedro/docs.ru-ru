---
title: Привязка данных
description: Узнайте, как использовать привязку данных в Windows Forms для отображения и внесения изменений в данные из источника данных в элементах управления в форме.
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: 3dfce24147caf9b138916ca8dc3b7a9010439f58
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325549"
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="e9334-103">Привязка данных Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9334-103">Windows Forms Data Binding</span></span>
<span data-ttu-id="e9334-104">Привязка данных в Windows Forms дает возможность отображать и изменять информацию из источника данных в элементах управления в форме.</span><span class="sxs-lookup"><span data-stu-id="e9334-104">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="e9334-105">В Windows Forms можно выполнить привязку не только к традиционным источникам данных, но и к практически к любой структуре, содержащий данные.</span><span class="sxs-lookup"><span data-stu-id="e9334-105">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e9334-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="e9334-106">In This Section</span></span>  
 [<span data-ttu-id="e9334-107">Связывание данных и Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9334-107">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)  
 <span data-ttu-id="e9334-108">Общие сведения о привязке данных в Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e9334-108">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="e9334-109">Источники данных, поддерживаемые Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9334-109">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="e9334-110">Описывает источники данных, которые можно использовать с Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e9334-110">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="e9334-111">Интерфейсы, относящиеся к привязке данных</span><span class="sxs-lookup"><span data-stu-id="e9334-111">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)  
 <span data-ttu-id="e9334-112">Описывает некоторые интерфейсы, используемые для привязки данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e9334-112">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="e9334-113">Практическое руководство. Навигация по набору данных, отображаемых в форме Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9334-113">How to: Navigate Data in Windows Forms</span></span>](how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="e9334-114">Показано, как перемещаться по элементам в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="e9334-114">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="e9334-115">Получение уведомления об изменении данных, связанных с элементом управления, в Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e9334-115">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="e9334-116">Описывает различные типы уведомлений об изменении для привязки данных Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="e9334-116">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="e9334-117">Практическое руководство. Реализация интерфейса INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="e9334-117">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="e9334-118">Показано, как реализовать интерфейс <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="e9334-118">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="e9334-119">Этот интерфейс сообщает связанному элементу управления об изменениях свойств бизнес-объекта</span><span class="sxs-lookup"><span data-stu-id="e9334-119">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="e9334-120">Практическое руководство. Применение шаблона PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="e9334-120">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="e9334-121">Показывает, как применить шаблон " *PropertyName*Changed" к свойствам Windows Forms пользовательского элемента управления.</span><span class="sxs-lookup"><span data-stu-id="e9334-121">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="e9334-122">Практическое руководство. Реализация интерфейса ITypedList</span><span class="sxs-lookup"><span data-stu-id="e9334-122">How to: Implement the ITypedList Interface</span></span>](how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="e9334-123">Показано, как задействовать обнаружение схемы для связываемого списка путем реализации интерфейса <xref:System.ComponentModel.ITypedList>.</span><span class="sxs-lookup"><span data-stu-id="e9334-123">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="e9334-124">Практическое руководство. Реализация интерфейса IListSource</span><span class="sxs-lookup"><span data-stu-id="e9334-124">How to: Implement the IListSource Interface</span></span>](how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="e9334-125">Показано, как реализовать интерфейс <xref:System.ComponentModel.IListSource>, чтобы создать связываемый класс, который не реализует <xref:System.Collections.IList>, но предоставляет список из другого расположения.</span><span class="sxs-lookup"><span data-stu-id="e9334-125">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="e9334-126">Практическое руководство. Синхронизация элементов управления, связанных с одним источником данных</span><span class="sxs-lookup"><span data-stu-id="e9334-126">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="e9334-127">Показано, как обрабатывать событие <xref:System.Windows.Forms.BindingSource.BindingComplete> для обеспечения синхронизация всех элементов управления, привязанных к источнику данных.</span><span class="sxs-lookup"><span data-stu-id="e9334-127">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="e9334-128">Практическое руководство. Правильное позиционирование выделенной строки в дочерней таблице</span><span class="sxs-lookup"><span data-stu-id="e9334-128">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="e9334-129">Показано, как обеспечить сохранение позиции выбранной строки дочерней таблицы при изменении поля родительской таблицы.</span><span class="sxs-lookup"><span data-stu-id="e9334-129">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="e9334-130">См. также [интерфейсы, связанные с привязкой данных](interfaces-related-to-data-binding.md), [как перемещать данные в Windows Forms](how-to-navigate-data-in-windows-forms.md)и [как создавать элементы управления с простой привязкой в форме Windows Forms](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="e9334-130">Also see [Interfaces Related to Data Binding](interfaces-related-to-data-binding.md), [How to: Navigate Data in Windows Forms](how-to-navigate-data-in-windows-forms.md), and [How to: Create a Simple-Bound Control on a Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e9334-131">Справочник</span><span class="sxs-lookup"><span data-stu-id="e9334-131">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="e9334-132">Описывает класс, представляющий связку между связываемым компонентом и источником данных.</span><span class="sxs-lookup"><span data-stu-id="e9334-132">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="e9334-133">Описывает класс, инкапсулирующий источник данных для привязки к элементам управления.</span><span class="sxs-lookup"><span data-stu-id="e9334-133">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e9334-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="e9334-134">Related Sections</span></span>  
 [<span data-ttu-id="e9334-135">Компонент BindingSource</span><span class="sxs-lookup"><span data-stu-id="e9334-135">BindingSource Component</span></span>](./controls/bindingsource-component.md)  
 <span data-ttu-id="e9334-136">Содержит список разделов, описывающих использование компонента <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="e9334-136">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="e9334-137">Элемент управления DataGridView</span><span class="sxs-lookup"><span data-stu-id="e9334-137">DataGridView Control</span></span>](./controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="e9334-138">Предоставляет список разделов, в которых демонстрируется использование связываемого элемента управления datagrid.</span><span class="sxs-lookup"><span data-stu-id="e9334-138">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="e9334-139">Также см. раздел [доступ к данным в Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e9334-139">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>
