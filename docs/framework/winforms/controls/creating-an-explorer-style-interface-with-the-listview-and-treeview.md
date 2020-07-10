---
title: Пошаговое руководство. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора
description: Узнайте, как создать интерфейс стиля обозревателя с элементами управления Windows Forms ListView и TreeView с помощью конструктора.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174631"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a>Пошаговое руководство. Создание интерфейса в стиле проводника с использованием элементов управления ListView и TreeView с помощью конструктора

Одним из преимуществ Visual Studio является возможность создания профессионально оформленных Windows Forms приложений в течение короткого промежутка времени. Распространенным сценарием является создание пользовательского интерфейса с <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> элементами управления и, которые похожи на проводник Windows в операционных системах Windows. Проводник Windows отображает иерархическую структуру файлов и папок на компьютере пользователя.

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a>Создание формы, содержащей элемент управления ListView и TreeView

1. В меню **Файл** укажите **Создать**, затем нажмите **Проект**.

2. В диалоговом окне **Новый проект** сделайте следующее:

    1. В категории выберите либо **Visual Basic** , либо **Visual C#**.

    2. В списке шаблонов выберите **Windows Forms приложение**.

3. Нажмите кнопку **OK**. Будет создан новый проект Windows Forms.

4. Добавьте в <xref:System.Windows.Forms.SplitContainer> форму элемент управления и задайте для его <xref:System.Windows.Forms.SplitContainer.Dock%2A> свойства значение <xref:System.Windows.Forms.DockStyle.Fill> .

5. Добавьте <xref:System.Windows.Forms.ImageList> именованный элемент `imageList1` в форму и используйте окно свойств, чтобы добавить два изображения: изображение папки и изображение документа в указанном порядке.

6. Добавьте <xref:System.Windows.Forms.TreeView> элемент управления с именем `treeview1` в форму и разместите его в левой части <xref:System.Windows.Forms.SplitContainer> элемента управления. В окно свойств `treeView1` выполните следующие действия.

    1. Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Задайте свойству <xref:System.Windows.Forms.TreeView.ImageList%2A> значение `imagelist1.`

7. Добавьте <xref:System.Windows.Forms.ListView> элемент управления с именем `listView1` в форму и разместите его в правой части <xref:System.Windows.Forms.SplitContainer> элемента управления. В окно свойств `listview1` выполните следующие действия.

    1. Задайте для свойства <xref:System.Windows.Forms.Control.Dock%2A> значение <xref:System.Windows.Forms.DockStyle.Fill>.

    2. Задайте для свойства <xref:System.Windows.Forms.ListView.View%2A> значение <xref:System.Windows.Forms.View.Details>.

    3. Откройте редактор коллекции Колумнхеадер, нажав кнопку с многоточием ( ![ ...) в окно свойств Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) в <xref:System.Windows.Forms.ListView.Columns%2A> свойстве **.** Добавьте три столбца и задайте <xref:System.Windows.Forms.ColumnHeader.Text%2A> для них свойства `Name` , `Type` и `Last Modified` соответственно. Нажмите кнопку **ОК** , чтобы закрыть диалоговое окно.

    4. Задайте свойству <xref:System.Windows.Forms.ListView.SmallImageList%2A> значение `imageList1.`

8. Реализуйте код, чтобы заполнить <xref:System.Windows.Forms.TreeView> узлы и подузлы. Добавьте этот код в `Form1` класс.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. Поскольку в предыдущем коде используется пространство имен System.IO, добавьте соответствующий оператор using или Import в верхней части формы.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. Вызовите метод Set-up из предыдущего шага в конструкторе формы или <xref:System.Windows.Forms.Form.Load> методе обработки событий. Добавьте этот код в конструктор формы.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. Обработайте <xref:System.Windows.Forms.TreeView.NodeMouseClick> событие для `treeview1` и реализуйте код **,** который заполняется `listview1` содержимым узла при щелчке узла. Добавьте этот код в `Form1` класс.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     Если вы используете C#, убедитесь, что у вас есть <xref:System.Windows.Forms.TreeView.NodeMouseClick> событие, связанное с методом обработки событий. Добавьте этот код в конструктор формы.

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a>Тестирование приложения

Теперь можно проверить форму, чтобы убедиться, что она ведет себя так, как ожидалось.

#### <a name="to-test-the-form"></a>Тестирование формы

- Нажмите клавишу F5 для запуска приложения.

     Вы увидите разделенную форму <xref:System.Windows.Forms.TreeView> , содержащую элемент управления, который отображает каталог проекта слева, и <xref:System.Windows.Forms.ListView> элемент управления с правой стороны с тремя столбцами. Можно просмотреть, <xref:System.Windows.Forms.TreeView> выбрав узлы каталога, и <xref:System.Windows.Forms.ListView> заполнится содержимым выбранного каталога.

## <a name="next-steps"></a>Next Steps

Это приложение предоставляет пример того, как можно использовать <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ListView> вместе элементы управления и. Дополнительные сведения об этих элементах управления см. в следующих разделах:

- [Практическое руководство. Добавление пользовательских данных в элемент управления TreeView или ListView (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [Практическое руководство. Добавление в элемент управления ListView возможностей поиска](how-to-add-search-capabilities-to-a-listview-control.md)

- [Практическое руководство. Подключение контекстного меню к узлу элемента управления TreeView](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [Элемент управления ListView](listview-control-windows-forms.md)
- [Практическое руководство. Добавление и удаление узлов элемента управления TreeView в Windows Forms](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [Практическое руководство. Добавление и удаление элементов с помощью элемента управления ListView в Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Практическое руководство. Добавление столбцов в элемент управления ListView в Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
