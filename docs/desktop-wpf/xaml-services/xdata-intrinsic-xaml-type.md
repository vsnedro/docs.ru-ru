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
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432794"
---
# <a name="xxdata-intrinsic-xaml-type"></a>Встроенный тип XAML x:XData
Позволяет разместить острова данных XML в рамках производства XAML. XML элементы внутри `x:XData` не должны рассматриваться процессорами XAML, как если бы они являются частью действующего пространства имен XAML по умолчанию или любого другого пространства имен XAML. `x:XData`может содержать произвольно хорошо сформированный XML.

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
|`elementDataRoot`|Единый корневой элемент замкнутого острова данных. Для большинства возможных потребителей XML, не имеющая ни одного корня, считается недействительным. В частности, требуется единый корень, если `x:XData` он предназначен в качестве источника данных XML для WPF или многих других технологий, которые используют источники XML для связывания данных.|
|`[elementData]`|Необязательный параметр. XML, представляющий данные XML. Любое количество элементов может содержаться в качестве данных элементов и вложенных элементов, которые могут содержаться в других элементах; однако применяются общие правила XML.|

## <a name="remarks"></a>Примечания

Элементы XML `x:XData` внутри объекта могут повторно декларировать все возможные пространства имен и префиксы, содержащие XMLDOM в данных.

Программный доступ к данным `x:XData` XML и типу XAML возможен в службах <xref:System.Windows.Markup.XData> .NET XAML через класс.

## <a name="wpf-usage-notes"></a>Примечания об использовании WPF

Объект `x:XData` в основном используется в качестве <xref:System.Windows.Data.XmlDataProvider>детского объекта объекта или же <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> в качестве объекта детского свойства (в XAML это обычно выражается в синтаксисе элемента свойства).

Данные должны обычно переопределять базовое пространство имен XML в пределах острова данных, чтобы быть новым пространством имен XML по умолчанию (установлено на пустую строку). Это проще всего для островов простых данных, потому что <xref:System.Windows.Data.Binding.XPath%2A> выражения, которые используются для ссылки и привязки к данным, могут избежать включения префиксов. Более сложные острова данных могут определить несколько префиксов для данных и использовать определенную префикс для пространства имен XML в корне. В этом случае <xref:System.Windows.Data.Binding.XPath%2A> все ссылки на выражения должны включать соответствующую префикс с картой имен. Для получения дополнительной информации [см.](../data/data-binding-overview.md)

Технически, `x:XData` может быть использован в качестве содержания любого свойства типа <xref:System.Xml.Serialization.IXmlSerializable>. Тем <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> не менее, является единственным заметным осуществления.

## <a name="see-also"></a>См. также

- <xref:System.Windows.Data.XmlDataProvider>
- [Обзор связывания данных](../data/data-binding-overview.md)
- [Привязка расширения разметки](../../framework/wpf/advanced/binding-markup-extension.md)
