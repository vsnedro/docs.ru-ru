---
title: Практическое руководство. Определение и создание ссылки на ресурс
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: e33c86b03d8b18113f3a15b3ab251753958ff5b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646513"
---
# <a name="how-to-define-and-reference-a-resource"></a>Практическое руководство. Определение и создание ссылки на ресурс

В этом примере показано, как определить ресурс [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]и ссылаться на него с помощью атрибута в.

## <a name="example"></a>Пример

Следующий пример определяет два типа <xref:System.Windows.Media.SolidColorBrush> ресурсов: ресурс <xref:System.Windows.Style> и несколько ресурсов. Ресурс <xref:System.Windows.Media.SolidColorBrush> `MyBrush` используется для обеспечения значения нескольких свойств, <xref:System.Windows.Media.Brush> каждый из которых занимает значение типа. <xref:System.Windows.Style> Ресурсы, `PageBackground` `TitleText` `Label` и каждый целевой определенный тип управления. Стили устанавливают различные свойства на целевых элементах управления, когда этот ресурс стиля ссылается на ключ ресурса и используется для установки <xref:System.Windows.FrameworkElement.Style%2A> свойства нескольких определенных элементов управления, определенных в. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]

Обратите внимание, что одно из свойств `Label` в сеттерах стиля также ссылается на `MyBrush` ресурс, определенный ранее. Это распространенный метод, но важно помнить, что ресурсы разбираются и вводятся в словарь ресурсов в порядке, который они дают. Ресурсы также запрашиваются в порядке, найденном в словаре, если вы используете [расширение StaticResource Markup,](staticresource-markup-extension.md) чтобы ссылаться на них в другом ресурсе. Убедитесь, что любой ресурс, на который вы ссылаетесь, определен ранее в рамках сбора ресурсов, чем там, где затем запрашивается этот ресурс. При необходимости можно обойти строгий порядок создания ссылок ресурсов, используя [расширение DynamicResource Markup Extension](dynamicresource-markup-extension.md) для ссылки на ресурс во время выполнения, но вы должны знать, что этот метод DynamicResource имеет последствия для производительности. Для получения подробной информации [см.](../../../desktop-wpf/fundamentals/xaml-resources-define.md)

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>См. также раздел

- [Ресурсы XAML](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Стилизация и использование шаблонов](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
