---
title: Как изменить типа курсора
description: Измените курсор указателя мыши для элемента и для приложения в Windows Presentation Foundation. Этот пример состоит из XAML и файла кода программной части.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: ce0bc290948a0e52e85f76ceb62a330b49fd87ea
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165967"
---
# <a name="how-to-change-the-cursor-type"></a>Как изменить типа курсора
В этом примере показано, как изменить элемент <xref:System.Windows.Input.Cursor> указателя мыши для конкретного элемента и для приложения.  
  
 Этот пример состоит из [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] файла и файла кода программной части.  
  
## <a name="example"></a>Пример  
 Создается пользовательский интерфейс, который состоит из, <xref:System.Windows.Controls.ComboBox> чтобы выбрать нужную <xref:System.Windows.Input.Cursor> пару <xref:System.Windows.Controls.RadioButton> объектов, чтобы определить, применяется ли изменение курсора только к одному элементу или к целому приложению, а <xref:System.Windows.Controls.Border> какой элемент является элементом, к которому применяется новый курсор.  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 В следующем коде создается <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> обработчик событий, который вызывается при изменении типа курсора в <xref:System.Windows.Controls.ComboBox> .  Оператор Switch фильтрует по имени курсора и задает <xref:System.Windows.FrameworkElement.Cursor%2A> свойство для с <xref:System.Windows.Controls.Border> именем *дисплайареа*.  
  
 Если для изменения курсора задано значение "целое приложение", <xref:System.Windows.Input.Mouse.OverrideCursor%2A> свойству элемента управления задается свойство <xref:System.Windows.FrameworkElement.Cursor%2A> <xref:System.Windows.Controls.Border> .  Это заставляет курсор измениться для всего приложения.  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a>См. также раздел

- [Общие сведения о входных данных](input-overview.md)
