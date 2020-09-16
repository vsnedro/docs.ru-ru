---
title: Встроенный тип XAML x:XData
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: d78c2fd63192dc499b119e5b038b92555511a695
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544808"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Встроенный тип XAML x:XData
Включает размещение островов XML-данных в рабочей среде XAML. XML-элементы внутри `x:XData` не должны обрабатываться обработчиками XAML так, как если бы они были частью действующего пространства имен XAML по умолчанию или любого другого пространства имен XAML. `x:XData` может содержать произвольный XML-файл правильного формата.

## <a name="xaml-object-element-usage"></a>Использование элемента объекта XAML

```xaml
<x:XData>
  <elementDataRoot>
    [elementData]
  </elementDataRoot>
</x:XData>
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|`elementDataRoot`|Единственный корневой элемент вложенного острова данных. Для большинства конечных потребителей XML, не имеющий одного корня, считается недопустимым. В частности, один корневой элемент необходим, если класс `x:XData` предназначен для использования в качестве источника данных XML для WPF или многих других технологий, использующих источники XML для привязки данных.|
|`[elementData]`|Необязательный элемент. XML, представляющий XML-данные. В качестве данных элемента может содержаться любое количество элементов, а вложенные элементы могут содержаться в других элементах. Однако применяются общие правила XML.|

## <a name="remarks"></a>Примечания

XML-элементы внутри `x:XData` объекта могут повторно объявить все возможные пространства имен и префиксы, содержащиеся в данных XMLDOM.

Программный доступ к XML-данным и `x:XData` встроенный тип XAML возможны в службах .NET XAML через <xref:System.Windows.Markup.XData> класс.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

`x:XData`Объект в основном используется в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider> (или) в качестве дочернего объекта <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> Свойства (в XAML это обычно выражается в синтаксисе элемента свойства).

Данные обычно должны переопределять базовое пространство имен XML в области данных, чтобы стать новым пространством имен XML по умолчанию (для которого задана пустая строка). Это проще всего для простых островов данных, поскольку <xref:System.Windows.Data.Binding.XPath%2A> выражения, используемые для ссылки на данные и привязки к ним, могут не включать префиксы. Более сложные острова данных могут определять несколько префиксов для данных и использовать конкретный префикс для пространства имен XML в корне. В этом случае все <xref:System.Windows.Data.Binding.XPath%2A> ссылки на выражения должны включать соответствующий префикс, сопоставленный с пространством имен. Дополнительные сведения см. в разделе [Общие сведения о привязке данных](../data/data-binding-overview.md).

Технически `x:XData` может использоваться в качестве содержимого любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable> . Однако <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> является единственной выразительной реализацией.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.XmlDataProvider>
- [Общие сведения о привязке данных](../data/data-binding-overview.md)
- [Привязка расширения разметки](/dotnet/desktop/wpf/advanced/binding-markup-extension)
