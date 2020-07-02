---
ms.openlocfilehash: 6da589057cebfbf3f67a46b8d49d3a61f037c4c7
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622280"
---
### <a name="crash-in-selector-when-removing-an-item-from-a-custom-incc-collection"></a>Сбой в селекторе при удалении элемента из пользовательской коллекции INCC

#### <a name="details"></a>Подробнее

<code>T:System.InvalidOperationException</code> может возникнуть в следующих сценариях:<ul><li>ItemsSource для <code>T:System.Windows.Controls.Primitives.Selector</code> является коллекцией с пользовательской реализацией <code>T:System.Collections.Specialized.INotifyCollectionChanged</code>.</li><li>Выбранный элемент удаляется из коллекции.</li><li>Для <code>T:System.Collections.Specialized.NotifyCollectionChangedEventArgs</code> установлено <code>P:System.Collections.Specialized.NotifyCollectionChangedEventArgs.OldStartingIndex</code> = –1 (что указывает на неизвестную позицию).</li></ul>Стек вызова исключения начинается в System.Windows.Threading.Dispatcher.VerifyAccess() в System.Windows.DependencyObject.GetValue(DependencyProperty dp) в System.Windows.Controls.Primitives.Selector.GetIsSelected(DependencyObject element). Это исключение может возникнуть в .Net Framework 4.5, если у приложения несколько потоков Dispatcher. В .Net Framework 4.7 исключение также может возникнуть в приложениях с одним потоком Dispatcher. Проблема устранена в .Net Framework 4.7.1.

#### <a name="suggestion"></a>Предложение

Выполните обновление до .NET Framework 4.7.1.

| name    | Значение       |
|:--------|:------------|
| Область   |Дополнительный номер|
|Version|4.7|
|Type|Среда выполнения|
