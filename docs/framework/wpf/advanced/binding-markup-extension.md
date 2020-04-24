---
title: Привязка расширения разметки
ms.date: 03/30/2017
f1_keywords:
- Binding
helpviewer_keywords:
- Binding markup extensions [WPF]
- XAML [WPF], Binding markup extension
ms.assetid: 83d6e2a4-1b0c-4fc8-bd96-b5e98800ab63
ms.openlocfilehash: c6a424e085c7499db08d0a7e6b652f45fb2cdd70
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644086"
---
# <a name="binding-markup-extension"></a>Привязка расширения разметки
Отдает значение свойства в пользу значения, связанного с данными, создавая промежуточный объект выражения и интерпретируя контекст данных, который применяется к элементу и его связыванию во время выполнения.  
  
## <a name="binding-expression-usage"></a>Использование связывания выражения  
  
```xaml  
<object property="{Binding}" .../>  
-or-  
<object property="{Binding  bindProp1=value1[, bindPropN=valueN]*}" ...  
/>  
-or-  
<object property="{Binding path}" .../>  
-or  
<object property="{Binding path[, bindPropN=valueN]*}" .../>  
```  
  
## <a name="syntax-notes"></a>Заметки о синтаксисе  
 В этих синтаксисов, `[]` и `*` не буквально. Они являются частью обозначения, чтобы указать, что можно использовать нулевые или более пары*значений* `,` *bindProp,*`=`с сепаратором между ними и предыдущими парами*значений* *bindProp.*`=`  
  
 Любое из свойств, перечисленных в разделе "Связывание свойств, которые могут быть <xref:System.Windows.Data.Binding> установлены с связывающим расширением" может быть установлено с использованием атрибутов элемента объекта. Тем не менее, это не совсем использование расширения разметки, <xref:System.Windows.Data.Binding>это просто общая обработка <xref:System.Windows.Data.Binding> XAML атрибутов, которые устанавливают свойства класса CLR. Другими `<Binding` словами,*значение* `"[` *bindProp1*`="` *bindPropN*`="`*valueN* `"]*/>` является эквивалентным синтаксисом для атрибутов использования <xref:System.Windows.Data.Binding> элемента объекта вместо использования `Binding` выражения. Чтобы узнать об использовании атрибута <xref:System.Windows.Data.Binding>XAML конкретных свойств, см. <xref:System.Windows.Data.Binding>  
  
## <a name="xaml-values"></a>Значения XAML  
  
|||  
|-|-|  
|`bindProp1, bindPropN`|Название или <xref:System.Windows.Data.BindingBase> <xref:System.Windows.Data.Binding> свойство установить. Не <xref:System.Windows.Data.Binding> все свойства могут `Binding` быть установлены с расширением, `Binding` а некоторые свойства установиться в выражении только с помощью дальнейших вложенных расширений разметки. Смотрите раздел "Связывание свойств, которые могут быть установлены с обязательным расширением".|  
|`value1, valueN`|Значение, которое следует задать для свойства. Обработка значения атрибута в конечном счете специфична для типа и логики конкретного <xref:System.Windows.Data.Binding> свойства, устанавливаемого.|  
|`path`|Строка пути, которая <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> устанавливает неявное свойство. Смотрите также [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).|  
  
## <a name="unqualified-binding"></a>Неквалифицированный (обязательный)  
 Использование, `{Binding}` отображаемое в <xref:System.Windows.Data.Binding> "Использовании привязки <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> выражения", создает объект со значениями по умолчанию, который включает в себя инициал. `null` Это по-прежнему полезно во многих <xref:System.Windows.Data.Binding> сценариях, поскольку созданный <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> может <xref:System.Windows.Data.Binding.Source%2A?displayProperty=nameWithType> полагаться на ключевые свойства связывания данных, такие как и устанавливаемый в контексте данных времени выполнения. Для получения дополнительной информации о концепции контекста данных [см.](../../../desktop-wpf/data/data-binding-overview.md)  
  
## <a name="implicit-path"></a>Неявный путь  
 Расширение `Binding` разметки используется <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> как концептуальное "свойство по умолчанию", где `Path=` не нужно отображаться в выражении. Если вы `Binding` указываете выражение с неявным путем, неявный `bindProp` = `value` путь должен <xref:System.Windows.Data.Binding> отображаться сначала в выражении, до любых других пар, где свойство указывается по имени. Например: `{Binding PathString}`где `PathString` строка, которая оценивается как <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType> значение <xref:System.Windows.Data.Binding> в созданном использованием расширения разметки. Вы можете приложить неявный путь с другими названными свойствами `{Binding LastName, Mode=TwoWay}`после сепаратора запятой, например, .  
  
## <a name="binding-properties-that-can-be-set-with-the-binding-extension"></a>Связывание свойств, которые могут быть установлены с связывающим расширением  
 Синтаксис, показанный в `bindProp` = `value` этой теме, использует общее приближение, <xref:System.Windows.Data.BindingBase> потому что есть много свойств чтения/записи или <xref:System.Windows.Data.Binding> которые могут быть установлены через расширение `Binding` разметки/ синтаксис выражения. Они могут быть установлены в любом порядке, за исключением неявного <xref:System.Windows.Data.Binding.Path%2A?displayProperty=nameWithType>. (У вас есть возможность явно `Path=`указать, и в этом случае он может быть установлен в любом порядке). В принципе, вы можете установить ноль или `bindProp` = `value` больше свойств в списке ниже, используя пары, разделенные запятыми.  
  
 Некоторые из этих значений свойств требуют типов объектов, которые не поддерживают преобразование родного типа из синтаксиса текста в XAML, и, таким образом, требуют расширения разметки для того, чтобы быть установленным в качестве значения атрибута. Проверьте раздел XAML Attribute Usage в библиотеке рамочного класса .NET для получения дополнительной информации; строка, используемая для синтаксиса атрибута XAML с или без дальнейшего использования `Binding` расширения разметки, в основном такая `bindProp` = `value` же, как и значение, указанное в выражении, за исключением того, что вы не размещаете кавычки вокруг каждого в `Binding` выражении.  
  
- <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>: строка, которая определяет возможную связывающую группу. Это относительно продвинутая обязательная концепция; см справочная страница для <xref:System.Windows.Data.BindingBase.BindingGroupName%2A>.  
  
- <xref:System.Windows.Data.Binding.BindsDirectlyToSource%2A>: Boolean, может `true` `false`быть либо или . Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.Converter%2A>: может быть `bindProp` = `value` установлен в качестве строки в выражении, но для этого требуется ссылка объекта на значение, например [расширение staticResource Markup.](staticresource-markup-extension.md) Значение в этом случае является экземпляром пользовательского класса преобразователя.  
  
- <xref:System.Windows.Data.Binding.ConverterCulture%2A>: установленный в выражении как идентификатор на основе стандартов; см. <xref:System.Windows.Data.Binding.ConverterCulture%2A>  
  
- <xref:System.Windows.Data.Binding.ConverterParameter%2A>: может быть `bindProp` = `value` установлен в качестве строки в выражении, но это зависит от типа пройденного параметра. При прохождении эталонного типа для значения для этого использования требуется ссылка объекта, например вложенное [расширение staticResource Markup.](staticresource-markup-extension.md)  
  
- <xref:System.Windows.Data.Binding.ElementName%2A>: взаимоисключающие против <xref:System.Windows.Data.Binding.RelativeSource%2A> и; <xref:System.Windows.Data.Binding.Source%2A> каждое из этих связывающих свойств представляет собой особую обязательную методологию. Смотрите [обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
- <xref:System.Windows.Data.BindingBase.FallbackValue%2A>: может быть `bindProp` = `value` установлен в качестве строки в выражении, но это зависит от типа передаваемого значения. При прохождении эталонного типа требуется ссылка на объект, например, вложенное [расширение StaticResource Markup.](staticresource-markup-extension.md)  
  
- <xref:System.Windows.Data.Binding.IsAsync%2A>: Boolean, может `true` `false`быть либо или . Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.Mode%2A>: *значение* является постоянным <xref:System.Windows.Data.BindingMode> названием из перечисления. Например, `{Binding Mode=OneWay}`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A>: Boolean, может `true` `false`быть либо или . Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A>: Boolean, может `true` `false`быть либо или . Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.NotifyOnValidationError%2A>: Boolean, может `true` `false`быть либо или . Значение по умолчанию — `false`.  
  
- <xref:System.Windows.Data.Binding.Path%2A>строка, описывающая путь в объект данных или общую модель объекта. Формат предоставляет несколько различных конвенций для обхода объектной модели, которые не могут быть адекватно описаны в этой теме. Смотрите [PropertyPath XAML Syntax](propertypath-xaml-syntax.md).  
  
- <xref:System.Windows.Data.Binding.RelativeSource%2A>: взаимоисключающие <xref:System.Windows.Data.Binding.Source%2A>по сравнению с и; <xref:System.Windows.Data.Binding.ElementName%2A> каждое из этих связывающих свойств представляет собой особую обязательную методологию. Смотрите [обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md). Требуется вложенное использование [relativeSource MarkupExtension](relativesource-markupextension.md) для указания значения.  
  
- <xref:System.Windows.Data.Binding.Source%2A>: взаимоисключающие против <xref:System.Windows.Data.Binding.RelativeSource%2A> и; <xref:System.Windows.Data.Binding.ElementName%2A> каждое из этих связывающих свойств представляет собой особую обязательную методологию. Смотрите [обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md). Требуется вложенное использование расширения, как правило, [расширение StaticResource Markup,](staticresource-markup-extension.md) которое относится к источнику данных объекта из словаря ресурсов с ключевыми ключами.  
  
- <xref:System.Windows.Data.BindingBase.StringFormat%2A>строка, описывающая конвенцию формата строки для связанных данных. Это относительно продвинутая обязательная концепция; см справочная страница для <xref:System.Windows.Data.BindingBase.StringFormat%2A>.  
  
- <xref:System.Windows.Data.BindingBase.TargetNullValue%2A>: может быть `bindProp` = `value` установлен в качестве строки в выражении, но это зависит от типа пройденного параметра. При прохождении эталонного типа для значения требуется ссылка объекта, например вложенное [расширение StaticResource Markup.](staticresource-markup-extension.md)  
  
- <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>: *значение* является постоянным <xref:System.Windows.Data.UpdateSourceTrigger> названием из перечисления. Например, `{Binding UpdateSourceTrigger=LostFocus}`. Конкретные элементы управления потенциально имеют различные значения по умолчанию для этого связывающего свойства. См. раздел <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A>: Boolean, может `true` `false`быть либо или . Значение по умолчанию — `false`. См. заметки.  
  
- <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A>: Boolean, может `true` `false`быть либо или . Значение по умолчанию — `false`. См. заметки.  
  
- <xref:System.Windows.Data.Binding.XPath%2A>строка, описывающая путь в XMLDOM источника данных XML. Смотрите [Привязка к данным XML с помощью XMLDataProvider и XPath запросы](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md).  
  
 Ниже приведены <xref:System.Windows.Data.Binding> свойства, которые не `Binding` могут быть`{Binding}` установлены с помощью расширения разметки / формы выражения.  
  
- <xref:System.Windows.Data.Binding.UpdateSourceExceptionFilter%2A>: это свойство ожидает ссылку на реализацию обратного вызова. Обратные вызовы/методы, помимо обработчиков событий, не могут быть отнесены в синтаксис XAML.  
  
- <xref:System.Windows.Data.Binding.ValidationRules%2A>: свойство занимает общий набор объектов. <xref:System.Windows.Controls.ValidationRule> Это может быть выражено как <xref:System.Windows.Data.Binding> элемент свойства в элементе объекта, но не имеет `Binding` легкодоступного метода разбора атрибутов для использования в выражении. Смотрите справочную <xref:System.Windows.Data.Binding.ValidationRules%2A>тему для .  
  
- <xref:System.Windows.Data.Binding.XmlNamespaceManager%2A>  
  
## <a name="remarks"></a>Примечания  
  
> [!IMPORTANT]
> С точки зрения приоритета свойства `Binding` зависимости выражение эквивалентно локально установленному значению. Если вы установите локальное значение для `Binding` свойства, `Binding` которое ранее имело выражение, то это полностью удаляется. Дополнительные сведения см. в разделе [Приоритет значений свойств зависимостей](dependency-property-value-precedence.md).  
  
 Описание связывания данных на базовом уровне не рассматривается в этой теме. Смотрите [обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md).  
  
> [!NOTE]
> <xref:System.Windows.Data.MultiBinding>и <xref:System.Windows.Data.PriorityBinding> не поддерживают [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] синтаксис расширения. Вместо этого можно использовать элементы свойств. Смотрите справочные <xref:System.Windows.Data.MultiBinding> <xref:System.Windows.Data.PriorityBinding>темы для и .  
  
 Значения Boolean для XAML являются нечувствительными. Например, вы `{Binding NotifyOnValidationError=true}` можете `{Binding NotifyOnValidationError=True}`указать либо или .  
  
 Привязки, связанные с проверкой `Binding` данных, `{Binding ...}` обычно определяются <xref:System.Windows.Data.Binding.ValidatesOnDataErrors%2A> <xref:System.Windows.Data.Binding.ValidatesOnExceptions%2A> явным элементом, а не выражением, а настройка или выражение являются редкостью. Это происходит потому, что свойство <xref:System.Windows.Data.Binding.ValidationRules%2A> компаньона не может быть легко установлено в форме выражения. Для получения дополнительной [Implement Binding Validation](../data/how-to-implement-binding-validation.md)информации см.  
  
 `Binding` является расширением разметки. Расширения разметки обычно реализуются, когда существует требование избеубежать значения атрибута, чтобы быть иными, чем буквальные значения или имена обработчиков, и требование является более глобальным, чем преобразователи типа, приписываемые определенным типам или свойствам. Все расширения разметки в `{` XAML используют и `}` символы в их синтаксисе атрибутов, который является конвенцией, по которой процессор XAML признает, что расширение разметки должно обрабатывать содержимое строки. Дополнительные сведения см. в разделе [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md).  
  
 `Binding`является нетипичным расширением разметки в том, что <xref:System.Windows.Data.Binding> класс, который реализует функциональность расширения для реализации XAML WPF, также реализует несколько других методов и свойств, не связанных с XAML. Другие участники призваны сделать <xref:System.Windows.Data.Binding> более универсальный и автономный класс, который может решать многие сценарии связывания данных в дополнение к функционированию в качестве расширения разметки XAML.  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Windows.Data.Binding>
- [Обзор связывания данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Обзор XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Расширения разметки и XAML WPF](markup-extensions-and-wpf-xaml.md)
