---
title: Практическое руководство. Создание привязки к методу
description: Выполните приведенный ниже пример, чтобы узнать, как выполнить привязку к методу объекта в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding to methods using ObjectDataProvider
- binding [WPF], to methods
- methods [WPF], binding to
ms.assetid: 5f55e71e-2182-42a0-88d1-700cc1427a7a
ms.openlocfilehash: 9501e6357203c21651e85f1d65059be1d70becf2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619602"
---
# <a name="how-to-bind-to-a-method"></a>Практическое руководство. Создание привязки к методу
В следующем примере показано, как выполнить привязку к методу с помощью <xref:System.Windows.Data.ObjectDataProvider> .  
  
## <a name="example"></a>Пример  
 В этом примере `TemperatureScale` — это класс, у которого есть метод `ConvertTemp`, принимающий два параметра (один из `double` и один из `enum` типа `TempType)`) и преобразующий данное значение из одной температурной шкалы в другую. В следующем примере <xref:System.Windows.Data.ObjectDataProvider> используется для создания экземпляра `TemperatureScale` объекта. Метод `ConvertTemp` вызывается с двумя заданными параметрами.  
  
 [!code-xaml[BindToMethod#WindowResources](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#windowresources)]  
  
 Теперь, когда метод доступен как ресурс, вы можете привязывать к его результатам. В следующем примере <xref:System.Windows.Controls.TextBox.Text%2A> свойство объекта <xref:System.Windows.Controls.TextBox> и <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A> объекта <xref:System.Windows.Controls.ComboBox> привязаны к двум параметрам метода. Таким образом, пользователи могут указывать исходную и целевую температурную шкалу. Обратите внимание, что <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A> свойство имеет значение, `true` поскольку привязка выполняется к <xref:System.Windows.Data.ObjectDataProvider.MethodParameters%2A> свойству <xref:System.Windows.Data.ObjectDataProvider> экземпляра, а не к свойствам объекта, упакованного объектом <xref:System.Windows.Data.ObjectDataProvider> ( `TemperatureScale` объектом).  
  
 <xref:System.Windows.Controls.ContentControl.Content%2A>Последнее <xref:System.Windows.Controls.Label> обновление, когда пользователь изменяет содержимое объекта <xref:System.Windows.Controls.TextBox> или выбор <xref:System.Windows.Controls.ComboBox> .  
  
 [!code-xaml[BindToMethod#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToMethod/CS/Window1.xaml#ui)]  
  
 Преобразователь `DoubleToString` принимает значение Double и превращает его в строку в <xref:System.Windows.Data.IValueConverter.Convert%2A> направлении (от источника привязки к целевому объекту привязки, который является <xref:System.Windows.Controls.TextBox.Text%2A> свойством) и преобразует в в `string` `double` <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> направлении.  
  
 `InvalidationCharacterRule`— Это объект <xref:System.Windows.Controls.ValidationRule> , который проверяет наличие недопустимых символов. Шаблон ошибок по умолчанию, который является красной границей вокруг <xref:System.Windows.Controls.TextBox> , отображается для уведомления пользователей о том, что входное значение не является значением типа Double.  
  
## <a name="see-also"></a>См. также

- [Практические руководства](data-binding-how-to-topics.md)
- [Привязка к перечислению](how-to-bind-to-an-enumeration.md)
