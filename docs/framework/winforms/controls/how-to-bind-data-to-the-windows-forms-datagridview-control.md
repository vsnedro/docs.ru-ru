---
title: Привязка данных к элементу управления DataGridView
ms.date: 02/08/2019
description: Узнайте, как элемент управления DataGridView поддерживает стандартную модель привязки данных Windows Forms, чтобы она могла выполнять привязку к различным источникам данных.
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 3c3502804d1bc4a5eeffc22b4ec5f2773411ef69
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904420"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a>Как привязать данные к элементу управления Windows Forms DataGridView

<xref:System.Windows.Forms.DataGridView>Элемент управления поддерживает стандартную модель привязки данных Windows Forms, поэтому она может выполнять привязку к различным источникам данных. Как правило, привязка выполняется к элементу <xref:System.Windows.Forms.BindingSource> , который управляет взаимодействием с источником данных. <xref:System.Windows.Forms.BindingSource>Может быть любым Windows Formsным источником данных, что обеспечивает большую гибкость при выборе или изменении расположения данных. Дополнительные сведения о том, какие источники данных <xref:System.Windows.Forms.DataGridView> поддерживает элемент управления, см. в разделе [Общие сведения об элементе управления DataGridView](datagridview-control-overview-windows-forms.md).  

Visual Studio обладает расширенной поддержкой привязки данных к элементу управления DataGridView. Дополнительные сведения см. в разделе [инструкции. Привязка данных к элементу управления Windows Forms DataGridView с помощью конструктора](bind-data-to-the-datagrid-using-the-designer.md).  

Подключение элемента управления DataGridView к данным:

1. Реализуйте метод для управления деталями извлечения данных. В следующем примере кода реализуется `GetData` метод, который инициализирует <xref:System.Data.SqlClient.SqlDataAdapter> и использует его для заполнения <xref:System.Data.DataTable> . Затем он привязывает <xref:System.Data.DataTable> к <xref:System.Windows.Forms.BindingSource> .

2. В <xref:System.Windows.Forms.Form.Load> обработчике событий формы привяжите <xref:System.Windows.Forms.DataGridView> элемент управления к <xref:System.Windows.Forms.BindingSource> и вызовите `GetData` метод для получения данных.  

## <a name="example"></a>Пример

Этот полный пример кода извлекает данные из базы данных для заполнения элемента управления DataGridView в форме Windows Forms. Форма также содержит кнопки для перезагрузки данных и отправки изменений в базу данных.  

Для этого примера требуются:

- Доступ к образцу базы данных Northwind SQL Server. Дополнительные сведения об установке образца базы данных Northwind см. [в статье получение образцов баз данных для ADO.NET кода](../../data/adonet/sql/linq/downloading-sample-databases.md).

- Ссылки на системные сборки, System. Windows. Forms, System. Data и System.Xml.  

Чтобы выполнить сборку и запуск этого примера, вставьте код в файл кода *Form1* в новом Windows Forms проекте. Сведения о построении из командной строки C# или Visual Basic см. в разделе Построение из командной строки [с помощью csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) или [Сборка из командной строки](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
Заполните `connectionString` переменную в примере значениями для образца подключения к базе данных Northwind SQL Server. Проверка подлинности Windows, называемая также встроенной безопасностью, является более безопасным способом подключения к базе данных, чем сохранение пароля в строке подключения. Дополнительные сведения о безопасности подключения см. в разделе [Защита сведений о подключении](../../data/adonet/protecting-connection-information.md).  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [Отображение данных в элементе управления Windows Forms DataGridView](displaying-data-in-the-windows-forms-datagridview-control.md)
- [Защита сведений о соединении](../../data/adonet/protecting-connection-information.md)
