---
title: Обработка xml:lang в XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], xml:lang attribute
- xml:lang attribute [XAML Services]
- RFC 3066 standard [XAML Services]
- standards [XAML Services], RFC 3066
ms.assetid: 7aac0078-a1c5-41f8-b8b0-975510d9dca0
ms.openlocfilehash: 92d1eda62ff394df54d9607bab46d9950681e603
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548212"
---
# <a name="xmllang-handling-in-xaml"></a>Обработка xml:lang в XAML

`xml:lang`Атрибут представляет собой XML-определенный атрибут, который объявляет сведения о языке и региональных параметрах для элемента в XML. Такое же значение атрибута сохраняется в XAML; однако действуют некоторые дополнительные факторы.

## <a name="xaml-attribute-usage"></a>Использование атрибута XAML

```xaml
<object xml:lang="rfc3066lang" />
```

## <a name="xaml-values"></a>Значения XAML

|||
|-|-|
|*rfc3066lang*|Строка, которая является производной от стандарта [RFC 3066](https://www.ietf.org/rfc/rfc3066.txt) и определяет язык или язык-регион. В последнем варианте язык и регион разделяются дефисом. Дополнительные сведения о значениях и формате см. в разделе <xref:System.Windows.Markup.XmlLanguage> .|

## <a name="remarks"></a>Примечания

Определение `xml:lang` атрибута в [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] является производным от, `xml:lang` определенного как "специальный атрибут" в консорциум W3C (W3C) for XML. Сведения о языке и региональных параметрах потенциально обрабатываются элементами по-разному, в зависимости от реализации этих элементов; однако обработка [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] атрибута `xml:lang` по умолчанию отсутствует.

Значение по умолчанию атрибута `xml:lang` представляет собой пустую строку на уровне атрибута.

Действие атрибута `xml:lang` и значение этого атрибута обычно сохраняются в дочерних элементах при интерпретации системами, которые работают со значениями `xml:lang` .

При интерпретации модулями записи XAML служб .NET XAML `xml:lang` значение может создавать <xref:System.Windows.Markup.XmlLanguage> <xref:System.Globalization.CultureInfo> объекты или в базовом представлении объекта, однако это поведение зависит от того, является ли значение, заданное для `xml:lang` , допустимой конструкцией для этих классов.

Инфраструктуры могут создавать связи между определенными инфраструктурой свойствами и значением `xml:lang` в XML, применяя <xref:System.Windows.Markup.XmlLangPropertyAttribute> к свойству.

## <a name="wpf-usage-nodes"></a>Узлы использования WPF

Для элементов, которые являются производными классами от <xref:System.Windows.FrameworkElement> или <xref:System.Windows.FrameworkContentElement>, можно использовать эквивалентное свойство зависимостей <xref:System.Windows.FrameworkElement.Language%2A> вместо атрибута `xml:lang` . По умолчанию свойство <xref:System.Windows.FrameworkElement.Language%2A> использует "en-US", если не установлено иное, посредством этого свойства или путем обработки атрибута `xml:lang` .

## <a name="see-also"></a>См. также

- [Глобализация для WPF](/dotnet/desktop/wpf/advanced/globalization-for-wpf)
