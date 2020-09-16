---
title: Атрибут x:Shared
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: d5000b51d83066ec2d529db2033d8ac54f7ad329
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557792"
---
# <a name="xshared-attribute"></a>Атрибут x:Shared

Если задано значение `false` , изменяет поведение извлечения ресурсов WPF, чтобы запросы к ресурсу с атрибутами создали новый экземпляр для каждого запроса вместо того, чтобы совместно использовать один и тот же экземпляр для всех запросов.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a>Примечания

`x:Shared` сопоставляется с пространством имен XAML языка XAML и распознается как допустимый элемент языка XAML службами XAML .NET и его средствами чтения XAML. Однако указанные возможности применимы `x:Shared` только для приложений WPF и средства синтаксического анализа XAML WPF. В WPF `x:Shared` может использоваться только в качестве атрибута, если он применяется к объекту, существующему в WPF <xref:System.Windows.ResourceDictionary> . Другие случаи использования не вызывают исключений синтаксического анализа или других ошибок, но не оказывают никакого влияния.

Значение параметра `x:Shared` не указано в спецификации языка XAML. Другие реализации XAML, такие как сборки на основе служб XAML .NET, не обязательно предоставляют поддержку общего доступа к ресурсам. Такие реализации XAML могут обеспечить аналогичное поведение в поддерживающей платформе, которая также использует `x:Shared` значения.

В WPF для ресурсов по умолчанию `x:Shared` используется условие `true` . Это условие означает, что любой заданный запрос ресурса всегда возвращает один и тот же экземпляр.

Изменение объекта, возвращаемого через API ресурсов, например <xref:System.Windows.FrameworkElement.FindResource%2A> , или путем изменения объекта непосредственно в <xref:System.Windows.ResourceDictionary> , изменяет исходный ресурс. Если ссылки на этот ресурс были динамическими ссылками на ресурсы, потребители этого ресурса получают измененный ресурс.

Если ссылки на ресурс были статическими ссылками на ресурсы, изменения ресурса после [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] времени обработки не имеют значения. Дополнительные сведения о статических и динамических ссылках на ресурс см. в разделе [ресурсы XAML](../fundamentals/xaml-resources-define.md).

Явное указание `x:Shared="true"` редко выполняется, так как оно уже используется по умолчанию. `x:Shared`В объектной модели WPF нет прямого эквивалента кода; его можно указать только в использовании XAML и обрабатывать либо с помощью поведения WPF по умолчанию, либо в промежуточном потоке узлов XAML по пути загрузки, если он обрабатывается с помощью служб XAML .NET и его средств чтения XAML.

Сценарий для `x:Shared="false"` имеет значение, если вы определяете <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement> производный класс в качестве ресурса, а затем вводит ресурс элемента в модель содержимого. `x:Shared="false"` позволяет вводить ресурс элемента несколько раз в одной коллекции (например, <xref:System.Windows.Controls.UIElementCollection> ). Без `x:Shared="false"` этого параметра не является допустимым, так как коллекция обеспечивает уникальность ее содержимого. Однако `x:Shared="false"` поведение создает еще один идентичный экземпляр ресурса вместо того, чтобы возвращать тот же экземпляр.

Другой сценарий для `x:Shared="false"` — Если для <xref:System.Windows.Freezable> значений анимации используется ресурс, но требуется изменить ресурс на основе анимации.

Обработка строк `false` не учитывает регистр.

В WPF `x:Shared` является допустимым только при следующих условиях:

- Объект <xref:System.Windows.ResourceDictionary> , содержащий элементы с, `x:Shared` должен быть скомпилирован. Объект <xref:System.Windows.ResourceDictionary> не может находиться в свободном XAML или использоваться для тем.

- Объект <xref:System.Windows.ResourceDictionary> , содержащий элементы, не должен быть вложен в другой <xref:System.Windows.ResourceDictionary> . Например, нельзя использовать `x:Shared` для элементов в <xref:System.Windows.ResourceDictionary> , которые находятся в элементе, <xref:System.Windows.Style> который уже является <xref:System.Windows.ResourceDictionary> элементом.

## <a name="see-also"></a>См. также

- <xref:System.Windows.ResourceDictionary>
- [Ресурсы XAML](../fundamentals/xaml-resources-define.md)
- [Базовые элементы](/dotnet/desktop/wpf/advanced/base-elements)
