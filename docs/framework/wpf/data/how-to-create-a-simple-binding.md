---
title: Практическое руководство. Создать простой привязки
description: Создайте простую привязку для приложений с помощью этого примера в Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 63dc44b442bb4658382bf12faf57b51c8e0698bb
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618705"
---
# <a name="how-to-create-a-simple-binding"></a>Практическое руководство. Создать простой привязки
В этом примере показано, как создать простой <xref:System.Windows.Data.Binding> .  
  
## <a name="example"></a>Пример  
 В этом примере у вас есть `Person` объект со строковым свойством с именем `PersonName` . `Person`Объект определяется в пространстве имен с именем `SDKSample` .  
  
 Выделенная строка, содержащая `<src>` элемент в следующем примере, создает экземпляр `Person` объекта со `PersonName` значением свойства `Joe` . Это делается в `Resources` разделе и назначено `x:Key` .  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 Выделенная строка, содержащая `<TextBlock>` элемент, привязывает <xref:System.Windows.Controls.TextBlock> элемент управления к `PersonName` свойству. В результате <xref:System.Windows.Controls.TextBlock> отображается со значением Joe.  
  
## <a name="see-also"></a>См. также

- [Общие сведения о привязке данных](../../../desktop-wpf/data/data-binding-overview.md)
- [Практические руководства](data-binding-how-to-topics.md)
